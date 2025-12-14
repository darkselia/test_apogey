<script setup>
import CtaButton from './CtaButton.vue';
import {ref} from 'vue';

const showTalentModal = ref(false);

const handleTalentSubmit = (payload) => {
  console.log('Talent request submitted', payload);
};
const content = {
  eyebrow: 'Сайт для будущих лидеров Апогея',
  title: 'Создаем карьеру в 1С вместе с теми, кто меняет отрасль',
  description:
      '«Апогей» 15 лет сопровождает более 3000 госучреждений по всей России: от Минфина и Минздрава Красноярского края до федеральных ведомств. Мы №7 среди 6800 партнёров 1С и продолжаем усиливаться.',
  promise:
      '550+ сотрудников в Красноярске, Краснодаре, Владивостоке, Самаре, Екатеринбурге и Иркутске. Запускаем офис в Санкт-Петербурге и растим ИТ-специалистов массово вместе с вузами (СФУ, СибГУ и др.).',
  video: {
    poster: '/src/assets/talent-hero.webp',
    src: 'https://www.w3schools.com/html/mov_bbb.mp4',
  },
  ctaPrimary: 'Записаться на карьерный трек',
  ctaSecondary: 'Смотреть культуру и события',
  stats: [
    {value: '3000+', label: 'госучреждений на сопровождении'},
    {value: '550+', label: 'сотрудников и стажёров в 6 городах'},
    {value: '№7 из 6800', label: 'партнёров 1С. Цель – стать №1'},
  ],
  dna: {
    title: 'ДНК Апогея',
    description: 'Культура, принципы и ценности, которые задают темп командам и продуктам.',
    values: [
      {
        title: 'Прозрачные лидерские лестницы',
        text: 'Каждый сотрудник видит свою траекторию роста, результаты и обратную связь в реальном времени.'
      },
      {
        title: 'Партнерство вместо иерархии',
        text: 'Менторы и топ-менеджеры доступны в open office, участвуют в код-ревью и продуктовых сессиях.'
      },
      {
        title: 'Смелые эксперименты',
        text: 'Любая идея тестируется в песочнице или на клиентском MVP с поддержкой наставника.'
      },
      {
        title: 'Осознанная ответственность',
        text: 'Мы доводим кейсы до результата и поддерживаем друг друга, когда сложно.'
      },
    ],
  },
  achievements: {
    title: 'Достигнутые результаты и замысел на будущее',
    timeline: [
      {year: '2022', text: 'Запустили Digital Internship Lab: 120 студентов прошли путь от стажировки до джуна.'},
      {year: '2023', text: 'Создали R&D-группы по 1С и AI-автоматизации, вывели 12 новых модулей для госсектора.'},
      {year: '2024', text: 'Открыли Product Leadership School и программу ротации по городам присутствия.'},
      {
        year: '2025 →',
        text: 'План: 1000 молодых специалистов в сообществе и запуск интерактивной платформы с задачами клиентов.'
      },
    ],
  },
  work: {
    title: 'Какие задачи мы решаем',
    description: 'Каждый трек — живой проект: реальные данные, пользователи и дедлайны.',
    cards: [
      {
        headline: '1С для клиник',
        text: 'Оптимизируем расчеты медучреждений: интеграция с МИС, прогнозирование закупок, отчетность для Минздрава.'
      },
      {
        headline: 'ФинТех для госсектора',
        text: 'Разрабатываем сервисы для региональных казначейств: онлайн-контроль закупок, бюджетирование, BI дешборды.'
      },
      {
        headline: 'AI-ассистенты для бухгалтеров',
        text: 'Создаем чат-ботов на базе исторических кейсов Апогея, которые помогают закрывать отчеты и проверять ошибки.'
      },
    ],
  },
  interactive: {
    title: 'Интерактив: попробуйте решать кейсы Апогея',
    description: 'Регистрация занимает 2 минуты. Вы получите доступ к реальным задачам клиентов в 1С, куратору и чек-листам проверки.',
    steps: [
      'Заполните мини-анкету и выберите направление (аналитика, разработка, консалтинг).',
      'Получите письмо с брифом и рабочей базой 1С (cloud) + чат с ментором.',
      'Решите задачу за 48 часов, защитите результат на онлайн-сессии и получите обратную связь + оффер.',
    ],
  },
  mentors: {
    title: 'Люди Апогея',
    description: 'Познакомьтесь с теми, кто создает культуру компании каждый день.',
    people: [
      {
        name: 'Мария Высоцкая',
        role: 'Head of Culture & DNA',
        quote: 'Мы строим среду, где студент с первой недели общается с партнерами и видит ценность своей работы.',
        tag: 'Культура',
      },
      {
        name: 'Игорь Трофимов',
        role: 'Lead R&D Engineer',
        quote: 'Соревнуемся в внутренних хакатонах и выкатываем best practices в продукты клиентов.',
        tag: 'R&D',
      },
      {
        name: 'Сабина Ершова',
        role: 'Client Experience Lead',
        quote: 'Мы не просто пишем код — мы помогаем главбухам спать спокойно и гордимся этим.',
        tag: 'CX',
      },
    ],
  },
  media: {
    title: 'Фото, видео и рилсы',
    items: [
      {label: 'Ворк-тур по офису', type: 'video'},
      {label: 'Репортаж с Demo Day', type: 'reel'},
      {label: 'Фотоистория Digital Internship Lab', type: 'gallery'},
      {label: 'Тур по кампусу на КРАСИНЕ', type: 'photo'},
    ],
  },
};
</script>

<template>
  <section class="panel">
    <header>
      <p class="panel__eyebrow">{{ content.eyebrow }}</p>
      <h1 class="panel__header">{{ content.title }}</h1>
    </header>

    <section class="panel__block">
      <article>
        <p class="panel__subtitle">{{ content.description }}</p>
        <p class="panel__promise">{{ content.promise }}</p>
        <div class="panel__cta">
          <CtaButton :label="content.ctaPrimary"/>
          <CtaButton :label="content.ctaSecondary" variant="secondary"/>
        </div>
        <div class="panel__stats">
          <div v-for="stat in content.stats" :key="stat.label" class="stat">
            <div class="stat__label">{{ stat.value }}</div>
            <div class="stat__text">{{ stat.label }}</div>
          </div>
        </div>
      </article>
      <div class="panel_image">
        <img
            src="/src/assets/talent.webp"
            alt="Иллюстрация команды поддержки Апогей, помогающей главбуху"
        />
      </div>
    </section>

    <section class="surface-card">
      <header>
        <h2>{{ content.dna.title }}</h2>
        <p>{{ content.dna.description }}</p>
      </header>
      <ul class="list-plain">
        <li v-for="value in content.dna.values" :key="value.title">
          <h3>{{ value.title }}</h3>
          <p>{{ value.text }}</p>
        </li>
      </ul>
    </section>
    <section class="surface-card">
      <h2>{{ content.achievements.title }}</h2>
      <ol class="list-plain timeline__list">
        <li v-for="item in content.achievements.timeline" :key="item.year">
          <span class="timeline__year">{{ item.year }}</span>
          <p>{{ item.text }}</p>
        </li>
      </ol>
    </section>
    <section class="surface-card">
      <header>
        <h2>{{ content.work.title }}</h2>
        <p>{{ content.work.description }}</p>
      </header>
      <div class="work__cards">
        <article v-for="card in content.work.cards" :key="card.headline" class="work-card">
          <h3>{{ card.headline }}</h3>
          <p>{{ card.text }}</p>
        </article>
      </div>
    </section>

    <section class="surface-card">
      <header>
        <h2>{{ content.mentors.title }}</h2>
        <p>{{ content.mentors.description }}</p>
      </header>
      <div class="mentors__grid">
        <article v-for="person in content.mentors.people" :key="person.name" class="mentor-card">
          <span class="mentor-card__tag">{{ person.tag }}</span>
          <h3>{{ person.name }}</h3>
          <p>{{ person.role }}</p>
          <p class="mentor-card__quote">{{ person.quote }}</p>
        </article>
      </div>
    </section>

    <section class="surface-card">
      <header>
        <h2>{{ content.media.title }}</h2>
      </header>
      <div class="media-hub__list">
        <article v-for="item in content.media.items" :key="item.label" class="media-card">
          <span>{{ item.type }}</span>
          <p>{{ item.label }}</p>
          <button type="button">Смотреть</button>
        </article>
      </div>
    </section>

    <TalentForm
        :open="showTalentModal"
        @update:open="showTalentModal = $event"
        @submit="handleTalentSubmit"
    />
  </section>
</template>

<style scoped>
.panel {
  display: flex;
  flex-direction: column;
  gap: 32px;
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
  border-radius: 28px;
  padding: 32px;
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.panel_image {
  display: flex;
  align-items: center;
  justify-content: center;
}

.panel_image img {
  max-width: 100%;
  border-radius: 18px;
}

.list-plain {
  list-style: none;
  margin: 0;
  padding: 0;
}

.dna-list li {
  padding: 12px 0;
  border-bottom: 1px solid rgba(31, 31, 36, 0.08);
}

.timeline__list li {
  border-left: 2px solid var(--color-primary);
  padding-left: 12px;
  margin-bottom: 12px;
}

.timeline__year {
  font-weight: 700;
  color: var(--color-primary);
}

.work__cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 16px;
}

.work-card {
  border: 1px solid rgba(31, 31, 36, 0.08);
  border-radius: 18px;
  padding: 16px;
  background: var(--color-white);
}

.mentors__grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
  gap: 16px;
}

.mentor-card {
  border: 1px solid rgba(31, 31, 36, 0.08);
  border-radius: 20px;
  padding: 16px;
  background: var(--color-white);
}

.mentor-card__tag {
  font-size: 12px;
  text-transform: uppercase;
  color: var(--color-primary);
}

.media-hub__list {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 16px;
}

.media-card {
  border: 1px solid rgba(31, 31, 36, 0.08);
  border-radius: 18px;
  padding: 16px;
  background: var(--color-primary-soft);
  display: flex;
  flex-direction: column;
  gap: 8px;
}

.media-card button {
  align-self: flex-start;
  border: none;
  background: none;
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
}
</style>
