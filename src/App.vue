<script setup>
import {ref} from 'vue';
import ClientsTab from './components/ClientsTab.vue';
import TalentTab from './components/TalentTab.vue';

const tabs = [
  {id: 'clients', label: 'Для клиентов'},
  {id: 'talent', label: 'Для сотрудников'},
];

const activeTab = ref('clients');
</script>

<template>
  <div class="page">
    <header class="header">
      <div class="header__logo">
        <img src="/src/assets/LogoFull.svg" alt="Логотип компании «Апогей»" class="logo-full"/>
        <div class="header__tagline">
          <span>Корпоративный сайт «Апогей»</span>
          <small>Техподдержка 1С для госсектора</small>
        </div>
      </div>
      <div class="header__tabs">
        <button
            v-for="tab in tabs"
            :key="tab.id"
            class="tab-button"
            :class="{ 'tab-button--active': tab.id === activeTab }"
            type="button"
            :aria-selected="tab.id === activeTab"
            @click="activeTab = tab.id"
        >
          {{ tab.label }}
        </button>
      </div>
    </header>

    <main>
    </main>

    <footer class="site-footer">
      <span>2025© Компания «Апогей»</span>
      <a href="mailto:info@apogey.ru">info@apogey.ru</a>
      <a href="tel:88002008089">8-800-200-8089</a>
    </footer>
  </div>
</template>

<style scoped>
.page {
  padding: clamp(1rem, 3vw, 2.5rem);
  display: flex;
  flex-direction: column;
  gap: clamp(1rem, 2vw, 1.5rem);;
}

.header {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
  gap: 1rem;
}

.header__logo {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.logo-full {
  width: clamp(160px, 20vw, 220px);
  height: auto;
}

.header__tagline span {
  display: block;
  font-size: 0.9rem;
  letter-spacing: 0.08em;
  text-transform: uppercase;
}

.header__tagline small {
  color: var(--color-text-soft);
}

.header__tabs {
  display: inline-flex;
  background: var(--color-tab-bg);
  border-radius: 999px;
  padding: 0.3rem;
  border: 1px solid var(--color-tab-border);
}

.tab-button {
  border: none;
  background: transparent;
  color: var(--color-tab-text);
  padding: 0.6rem 1.6rem;
  border-radius: 999px;
  font-size: 16px;
  font-weight: 600;
  cursor: pointer;
  transition: color 0.3s ease, background 0.3s ease;
}

.tab-button--active {
  background: var(--color-primary-soft);
  color: var(--color-primary);
  box-shadow: 0 8px 20px rgba(255, 48, 1, 0.28);
}

.site-footer {
  margin-top: 1rem;
  display: flex;
  flex-direction: row;
  justify-content: space-around;
  text-align: center;
  color: var(--color-text-muted);
  gap: 0.35rem;
  font-size: 0.95rem;
}

.site-footer a {
  color: var(--color-text-muted);
  text-decoration: none;
}

</style>
