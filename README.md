# Тестовое задание в Apogey

Титульная страница для будущего корпоративного сайта 

## Ссылки
- Код: https://github.com/darkselia/test_apogey
- Деплой (Cloudflare Pages, может требовать VPN): https://test-apogey.pages.dev/

## Ключевые блоки
- **Clients** — сервис сопровождения 1С, ценностное предложение, статистика, статьи-инструкции, отзывы.
- **Talent** — вкладка для соискателей с ДНК компании, карьерными треками, интерактивной формой отклика и карточками менторов.
- **Глобальная стилистика** — единая система панелей/карт, табы, CTA, адаптация под требования из ТЗ.

## Стек
- [Vue 3](https://vuejs.org/) (Composition API + `<script setup>`)
- [Vite](https://vite.dev/) (dev server и сборка)
- CSS-модули на уровне компонентов, без дополнительных UI-библиотек

## Требования
- Node.js ^20.19.0 или >=22.12.0 (см. `package.json` → `engines`)
- npm (идёт вместе с Node)

## Локальный запуск
```bash
npm install
npm run dev
```
Dev-сервер доступен по адресу, указанному в консоли (по умолчанию http://localhost:5173).

## Сборка и предпросмотр
```bash
npm run build
npm run preview
```
`npm run build` генерирует production-бандл в `dist/`, `npm run preview` поднимает локальный сервер для проверки собранной версии.

## Структура проекта
```
apogey/
├─ src/
│  ├─ components/
│  │  ├─ ClientsTab.vue
│  │  ├─ TalentTab.vue
│  │  ├─ ClientForm.vue / TalentForm.vue и др.
│  ├─ App.vue
│  └─ main.js
├─ public/
├─ package.json
└─ vite.config.js
```

## Дополнительно
- Логотип взят с текущего сайта компании «Апогей».
- Копирайтинг подготовлен на основе ТЗ и данных из публичных источников компании.
- Деплой выполняется в Cloudflare Pages; для просмотра может потребоваться VPN.
