<script setup>
import CtaButton from './CtaButton.vue';
import {reactive, ref} from 'vue';

const props = defineProps({
  open: {
    type: Boolean,
    default: false,
  },
});

const emit = defineEmits(['update:open', 'submit']);

const form = reactive({
  name: '',
  email: '',
  organization: '',
  message: '',
});

const submitting = ref(false);

const resetForm = () => {
  Object.keys(form).forEach((key) => {
    form[key] = '';
  });
};

const closeModal = () => {
  resetForm();
  emit('update:open', false);
};

const handleSubmit = async () => {
  if (submitting.value) return;
  submitting.value = true;
  try {
    emit('submit', {...form});
    closeModal();
  } finally {
    submitting.value = false;
  }
};
</script>

<template>
  <div v-if="props.open" class="modal" role="dialog" aria-modal="true">
    <div class="modal__backdrop" @click="closeModal" />
    <section class="modal__card">
      <header class="modal__header">
        <div>
          <p class="modal__eyebrow">Заявка на сопровождение</p>
          <h2>Начните с трёх бесплатных вопросов</h2>
          <p class="modal__subtitle">Заполните форму, и в течение рабочего часа с вами свяжется персональный куратор Апогея.</p>
        </div>
        <button class="modal__close" type="button" aria-label="Закрыть" @click="closeModal">×</button>
      </header>
      <form class="modal__form" @submit.prevent="handleSubmit">
        <label class="modal__field">
          <span>ФИО</span>
          <input v-model="form.name" type="text" placeholder="Анна Иванова" required />
        </label>
        <label class="modal__field">
          <span>Email</span>
          <input v-model="form.email" type="email" placeholder="you@example.com" required />
        </label>
        <label class="modal__field">
          <span>Организация</span>
          <input v-model="form.organization" type="text" placeholder="ГУ Красноярского края" required />
        </label>
        <label class="modal__field">
          <span>Опишите задачу</span>
          <textarea v-model="form.message" rows="4" placeholder="Расскажите, с какой задачей по 1С нужна помощь"></textarea>
        </label>
        <CtaButton
            class="modal__submit"
            :label="submitting ? 'Отправляем…' : 'Отправить заявку'"
            :disabled="submitting"
        />
      </form>
    </section>
  </div>
</template>

<style scoped>
.modal {
  position: fixed;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 16px;
  z-index: 1000;
}

.modal__backdrop {
  position: absolute;
  inset: 0;
  background: rgba(11, 14, 26, 0.65);
  backdrop-filter: blur(6px);
}

.modal__card {
  position: relative;
  z-index: 1;
  width: min(600px, 100%);
  background: var(--color-white);
  border: 1px solid rgba(31, 31, 36, 0.08);
  border-radius: 32px;
  padding: clamp(24px, 4vw, 40px);
  box-shadow: 0 40px 70px rgba(15, 18, 32, 0.45);
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.modal__header {
  display: flex;
  gap: 16px;
  justify-content: space-between;
}

.modal__eyebrow {
  text-transform: uppercase;
  letter-spacing: 0.14em;
  font-size: 13px;
  color: var(--color-primary);
  margin: 0 0 6px;
}

.modal__subtitle {
  margin: 8px 0 0;
  color: var(--color-text-muted);
}

.modal__close {
  border: none;
  background: rgba(0, 0, 0, 0.04);
  border-radius: 50%;
  width: 40px;
  height: 40px;
  font-size: 24px;
  line-height: 1;
  cursor: pointer;
  align-self: flex-start;
}

.modal__form {
  display: grid;
  gap: 16px;
}

.modal__field {
  display: flex;
  flex-direction: column;
  gap: 8px;
  font-size: 14px;
  color: var(--color-text);
}

.modal__field input,
.modal__field textarea {
  border-radius: 16px;
  border: 1px solid var(--color-panel-border);
  padding: 12px 16px;
  font-size: 15px;
  transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

.modal__field input:focus-visible,
.modal__field textarea:focus-visible {
  border-color: var(--color-primary);
  box-shadow: 0 0 0 3px rgba(255, 48, 1, 0.12);
  outline: none;
}

.modal__submit {
  align-self: flex-start;
}

@media (width <= 600px) {
  .modal__header {
    flex-direction: column;
  }

  .modal__close {
    align-self: flex-end;
  }
}
</style>
