<script setup>
import CtaButton from './CtaButton.vue';

const content = {
  eyebrow: '№ 1 техподдержка 1С для бухгалтера госучреждения',
  title: 'Профессиональная поддержка 1С для госучреждений',
  subtitle:
      'Апогей обеспечивает надежный бухгалтерский сервис для государственных организаций по всей стране, решая самые сложные задачи в 1С.',
  promise: 'Решим три любых ваших вопроса по 1С в обмен на договор и запустим безлимитное сопровождение по фиксированной цене.',
  ctaPrimary: 'Оставить заявку на сопровождение',
  ctaSecondary: 'Смотреть кейсы и инструкции',
  stats: [
    {value: '631 685', label: 'задач решено за 12 месяцев'},
    {value: '24/7', label: 'помогаем вечерами и в выходные'},
    {value: '№1', label: 'по техподдержке 1С для госсектора'},
  ],
  valueTitle: 'Что получаете как заказчик',
  valueIntro:
      'Строим для вас безупречный сервис техподдержки 1С: сопровождаем до «победного», работаем во всех часовых поясах и берем ответственность за результат.',
  valueBullets: [
    'Безлимитный формат обслуживания — решаем неограниченное количество задач за фиксированную стоимость.',
    'Закрываем любые вопросы по 1С: бухгалтерия, зарплата, медицина и другие отраслевые решения.',
    'Подключаем персональную команду кураторов и делимся базой готовых решений и пошаговых инструкций.',
    'Помогаем с отчетностью по вечерам и в выходные и держим связь с бухгалтером до полного закрытия задачи.',
  ],
  guides: {
    kicker: 'Статьи-инструкции',
    headline: '10 пошаговых инструкций, как в 1С найти ошибки ведения учета',
    description: 'Собрали короткие материалы со скриншотами: ищем ошибку, показываем путь в интерфейсе и даём чек-лист, чтобы бухгалтер сразу исправил документ.',
    articles: [
      {title: 'Пятиминутная проверка перед сдачей баланса', date: '20 января 2025 г.'},
      {title: 'Главные ловушки учета основных средств', date: '15 февраля 2025 г.'},
      {title: 'Как проверить правильность закрытия прошлого года', date: '5 марта 2025 г.'},
      {title: 'Как обезопасить себя от случайных ошибок?', date: '28 апреля 2025 г.'},
      {title: 'Ошибки 303.00, влияющие на отчетность', date: '20 октября 2025 г.'},
      {title: 'Настройка суммированного учета рабочего времени', date: '17 ноября 2025 г.'},
      {title: 'Подготовиться к сдаче 769 за 5 минут', date: '7 мая 2025 г.'},
      {title: 'Детализация КОСГУ по типам контрагентов', date: '22 сентября 2025 г.'},
    ],
  },
  showcaseTitle: 'Решаем задачи в продуктах 1С',
  showcaseItems: [
    '1С:Бухгалтерия государственного учреждения',
    '1С:Зарплата и кадры государственного учреждения',
    '1С:Медицина. Больничная аптека',
  ],
  highlights: [
    'Экспертиза в узких регламентах и требованиях госсектора',
    'Персональные команды кураторов и круглосуточная поддержка',
    'База знаний с пошаговыми инструкциями и видео',
  ],
  testimonials: [
    {
      quote:
          '«Апогей» берет на себя сложнейшие вопросы в 1С и помогает сдавать отчетность без срывов – это настоящая страховка для главбуха.',
      author: 'Главный бухгалтер, Министерство финансов Красноярского края',
    },
    {
      quote:
          'За 3 дня решили задачу, с которой мы не могли справиться месяцами. Впечатляют глубина знаний и скорость реакции команды.',
      author: 'Руководитель УД Губернатора Красноярского края',
    },
  ],
  reviewLinks: [
    {
      label: 'Google',
      href: 'https://www.google.com/maps/search/%D0%B0%D0%BF%D0%BE%D0%B3%D0%B5%D0%B9+%D0%9A%D1%80%D0%B0%D1%81%D0%BD%D0%BE%D1%8F%D1%80%D1%81%D0%BA'
    },
    {
      label: 'Яндекс',
      href: 'https://yandex.ru/maps/62/krasnoyarsk/search/%D0%B0%D0%BF%D0%BE%D0%B3%D0%B5%D0%B9%20%D0%BA%D1%80%D0%B0%D1%81%D0%BD%D0%BE%D1%8F%D1%80%D1%81%D0%BA'
    },
    {
      label: '2ГИС',
      href: 'https://2gis.ru/search/%D0%B0%D0%BF%D0%BE%D0%B3%D0%B5%D0%B9/%D0%BE%D1%82%D0%B7%D1%8B%D0%B2%D1%8B'
    },
    {label: 'Фламп', href: 'https://flamp.ru/search/%D0%B0%D0%BF%D0%BE%D0%B3%D0%B5%D0%B9'},
  ],
};
</script>

<template>
  <section class="panel" aria-live="polite">
    <header>
      <p class="panel__eyebrow">{{ content.eyebrow }}</p>
      <h1 class="panel__header">{{ content.title }}</h1>
    </header>
    <section class="panel__block">
      <article>
        <p class="panel__subtitle">{{ content.subtitle }}</p>
        <p class="panel__promise">{{ content.promise }}</p>
        <div class="panel__cta">
          <CtaButton :label="content.ctaPrimary" />
          <CtaButton :label="content.ctaSecondary" variant="secondary" />
        </div>
        <div class="panel__stats">
          <div v-for="item in content.stats" :key="item.label" class="stat">
            <div class="stat__label">{{ item.value }}</div>
            <div class="stat__text">{{ item.label }}</div>
          </div>
        </div>
      </article>
      <div class="surface-card surface-card--visual">
        <img
            src="/src/assets/clients.webp"
            alt="Иллюстрация команды поддержки Апогей, помогающей главбуху"
        />
      </div>
    </section>

    <section class="panel__block">
      <article class="surface-card highlights">
        <header>
          <h2>{{ content.valueTitle }}</h2>
          <p>{{ content.valueIntro }}</p>
        </header>
        <ul class="highlights__list list-plain">
          <li v-for="(point, index) in content.valueBullets" :key="index">{{ point }}</li>
        </ul>
      </article>

      <article class="surface-card testimonials">
        <h2>Нам доверяют</h2>
        <TransitionGroup name="cascade" tag="div" class="testimonials__list">
          <article v-for="item in content.testimonials" :key="item.author">
            <p class="quote">«{{ item.quote }}»</p>
            <p class="author">{{ item.author }}</p>
          </article>
        </TransitionGroup>
        <h4>Отзывы в различных сервисах</h4>
        <ul class="review-links list-plain">
          <li v-for="link in content.reviewLinks" :key="link.label">
            <a
                class="review-link"
                :href="link.href"
                target="_blank"
            >
              {{ link.label }}
            </a>
          </li>
        </ul>
      </article>
    </section>

    <section class="surface-card modules">
      <h3>{{ content.showcaseTitle }}</h3>
      <ul class="modules__tags list-plain">
        <li v-for="item in content.showcaseItems" :key="item" class="tag">{{ item }}</li>
      </ul>
      <CtaButton :label="content.ctaPrimary" />
    </section>

    <section class="knowledge">
      <header class="knowledge__intro">
        <p class="knowledge__kicker">{{ content.guides.kicker }}</p>
        <h3>{{ content.guides.headline }}</h3>
        <p>{{ content.guides.description }}</p>
      </header>
      <div class="knowledge__articles">
        <article v-for="article in content.guides.articles" :key="article.title" class="article-card">
          <header>
            <h4>{{ article.title }}</h4>
            <span class="article-card__date">{{ article.date }}</span>
          </header>
          <button class="guide-card__cta">Читать инструкцию</button>
        </article>
      </div>
    </section>
  </section>
</template>

<style scoped>
.panel {
  background: var(--color-white);
  border: 1px solid var(--color-panel-border);
  border-radius: 32px;
  padding: clamp(24px, 3vw, 48px);
  display: flex;
  flex-direction: column;
  gap: clamp(24px, 3vw, 40px);
  box-shadow: 0 30px 60px rgba(18, 19, 26, 0.08);
}

.panel__block {
  display: grid;
  grid-template-columns: repeat(2, minmax(320px, 1fr));
  gap: 40px;
  align-items: center;
}

.panel__eyebrow {
  font-size: 13px;
  text-transform: uppercase;
  color: var(--color-primary);
}

.panel__header {
  font-size: clamp(32px, 4vw, 51px);
  margin: 0;
}

.panel__subtitle {
  color: var(--color-text-muted);
  line-height: 1.6;
  margin-bottom: 20px;
}

.panel__promise {
  background: var(--color-primary-soft);
  border-left: 4px solid var(--color-primary);
  padding: 13px 16px;
  border-radius: 12px;
  color: var(--color-chip-text);
  margin-bottom: 24px;
}

.panel__cta {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  margin-bottom: 32px;
}

.panel__stats {
  display: flex;
  flex-wrap: wrap;
  gap: 24px;
  justify-content: center;
}

.stat {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.stat__label {
  font-size: 24px;
  font-weight: 700;
}

.stat__text {
  color: var(--color-text-muted);
  margin: 0;
}

.surface-card {
  background: var(--color-surface);
  border: 1px solid var(--color-panel-border);
  border-radius: 24px;
  padding: 24px;
}

.surface-card--visual {
  display: flex;
  align-items: center;
  justify-content: center;
}

.surface-card--visual img {
  max-width: 100%;
  border-radius: 18px;
}

.list-plain {
  list-style: none;
  margin: 0;
  padding: 0;
}

.highlights__list {
  margin-top: 16px;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.highlights__list li {
  display: flex;
  gap: 10px;
  align-items: flex-start;
}

.highlights__list li::before {
  content: '';
  flex-shrink: 0;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: var(--color-primary);
  margin-top: 6px;
}

.testimonials__list {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.quote {
  font-style: italic;
  font-size: 16px;
  color: #3f4252;
  margin: 0;
}

.author {
  margin: 3px 0 0;
  font-size: 13px;
  color: #7b7e8b;
}

.review-links {
  display: flex;
  flex-wrap: wrap;
  gap: 16px;
  margin-top: 32px;
}

.review-link {
  background: var(--color-primary-soft);
  color: var(--color-chip-text);
  padding: 9px 19px;
  border-radius: 999px;
  font-weight: 500;
  text-decoration: none;
  transition: background 0.3s ease, transform 0.3s ease;
}

.modules__tags {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  margin-bottom: 32px;
}

.tag {
  padding: 7px 15px;
  border-radius: 999px;
  background: var(--color-primary-soft);
  color: var(--color-chip-text);
  font-weight: 600;
}

.knowledge {
  background: var(--color-white);
  border: 1px solid var(--color-panel-border);
  border-radius: 28px;
  padding: 28px;
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.knowledge__intro {
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.knowledge__kicker {
  text-transform: uppercase;
  letter-spacing: 1.28px;
  color: var(--color-primary);
  font-size: 13px;
  margin: 0 0 6px;
}

.knowledge__articles {
  display: grid;
  grid-template-columns: repeat(2, minmax(240px, 1fr));
  gap: 16px;
}

.article-card {
  border: 1px solid rgba(31, 31, 36, 0.08);
  border-radius: 20px;
  padding: 19px;
  background: var(--color-article-bg);
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.article-card h4 {
  margin: 0 0 5px;
  font-size: 16px;
  line-height: 1.3;
}

.article-card__date {
  font-size: 13px;
  color: var(--color-text-muted);
}

.guide-card__cta {
  align-self: flex-start;
  border: none;
  background: transparent;
  color: var(--color-primary);
  font-weight: 600;
  cursor: pointer;
}

@media (width <= 900px) {
  .panel__block {
    grid-template-columns: 1fr;
  }

  .panel__stats {
    flex-direction: column;
    align-items: center;
  }

  .knowledge__articles {
    grid-template-columns: 1fr;
  }
}
</style>
