<script setup>
import {computed} from 'vue';

const props = defineProps({
  label: {
    type: String,
    default: '',
  },
  variant: {
    type: String,
    default: 'primary',
  },
});

const variantClass = computed(() => {
  switch (props.variant) {
    case 'secondary':
      return 'cta--secondary';
    default:
      return 'cta--primary';
  }
});
</script>

<template>
  <button
      type="button"
      class="cta"
      :class="variantClass"
      v-bind="$attrs"
  >
    <slot>{{ label }}</slot>
  </button>
</template>

<style scoped>
.cta {
  border: none;
  border-radius: 999px;
  padding: 13px 28px;
  font-weight: 600;
  font-size: 16px;
  cursor: pointer;
  transition: transform 0.25s ease, box-shadow 0.25s ease, background 0.25s ease;
}

.cta--primary {
  background: linear-gradient(135deg, var(--color-primary), var(--color-primary-accent));
  color: var(--color-white);
  box-shadow: 0 12px 25px rgba(255, 68, 0, 0.35);
}

.cta--secondary{
  background: var(--color-white);
  color: var(--color-dark);
  border: 1px solid rgba(31, 31, 36, 0.15);
}

.cta:hover,
.cta:focus-visible {
  transform: translateY(-2px);
  box-shadow: 0 18px 30px rgba(255, 68, 0, 0.25);
}
</style>

