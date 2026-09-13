<script setup lang="ts">
const features = [
  {
    icon: "ai",
    title: "Интеллектуальное сравнение",
    description:
      "Анализ признаковых представлений и определение степени сходства трехмерных объектов.",
  },
  {
    icon: "search",
    title: "Поиск аналогов",
    description:
      "Ранжированный перечень ближайших моделей по рассчитанному коэффициенту сходства.",
  },
  {
    icon: "normalize",
    title: "Нормализация",
    description:
      "Приведение объектов к единому внутреннему представлению перед сравнением.",
  },
  {
    icon: "database",
    title: "Хранение данных",
    description:
      "Раздельное хранение исходных моделей, признаков и результатов интеллектуального анализа.",
  },
  {
    icon: "security",
    title: "Безопасный доступ",
    description:
      "Аутентификация, авторизация, разграничение прав и контроль целостности файлов.",
  },
  {
    icon: "api",
    title: "Масштабирование",
    description:
      "Модульная архитектура и возможность интеграции с внешними информационными системами.",
  },
];
</script>

<template>
  <section class="features">
    <div class="container">
      <div id="features" class="features__grid anchor-target">
        <article
          v-for="feature in features"
          :key="feature.title"
          class="feature card"
        >
          <div class="feature__icon">
            <svg v-if="feature.icon === 'ai'" viewBox="0 0 24 24">
              <rect x="5" y="5" width="14" height="14" rx="3" />
              <path d="M9 9v6M15 9v6M9 12h6" />
              <path d="M9 2v3M15 2v3M9 19v3M15 19v3" />
              <path d="M2 9h3M2 15h3M19 9h3M19 15h3" />
            </svg>

            <svg v-else-if="feature.icon === 'search'" viewBox="0 0 24 24">
              <circle cx="10.5" cy="10.5" r="6.5" />
              <path d="M15.5 15.5L21 21" />
            </svg>

            <svg v-else-if="feature.icon === 'normalize'" viewBox="0 0 24 24">
              <path d="M8 3H3v5" />
              <path d="M3 3l6 6" />
              <path d="M16 21h5v-5" />
              <path d="M21 21l-6-6" />
              <path d="M21 8V3h-5" />
              <path d="M21 3l-6 6" />
              <path d="M3 16v5h5" />
              <path d="M3 21l6-6" />
            </svg>

            <svg v-else-if="feature.icon === 'database'" viewBox="0 0 24 24">
              <ellipse cx="12" cy="5" rx="8" ry="3" />
              <path d="M4 5v7c0 1.7 3.6 3 8 3s8-1.3 8-3V5" />
              <path d="M4 12v7c0 1.7 3.6 3 8 3s8-1.3 8-3v-7" />
            </svg>

            <svg v-else-if="feature.icon === 'security'" viewBox="0 0 24 24">
              <path
                d="M12 3l7 3v5c0 4.6-2.8 8.4-7 10-4.2-1.6-7-5.4-7-10V6l7-3z"
              />
              <path d="M9 12l2 2 4-4" />
            </svg>

            <svg v-else viewBox="0 0 24 24">
              <path d="M8 8L4 12l4 4" />
              <path d="M16 8l4 4-4 4" />
              <path d="M14 5l-4 14" />
            </svg>
          </div>

          <h3 class="feature__title">
            {{ feature.title }}
          </h3>

          <p class="feature__description">
            {{ feature.description }}
          </p>
        </article>
      </div>
    </div>
  </section>
</template>

<style scoped>
.features {
  padding-bottom: var(--space-section);
}

.features__grid {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 16px;
}

.feature {
  padding: 28px;

  transition:
    transform 0.2s ease,
    border-color 0.2s ease;
}

.feature:hover {
  transform: translateY(-4px);

  border-color: rgb(103 232 249 / 25%);
}

.feature__icon {
  width: 44px;
  height: 44px;

  display: grid;
  place-items: center;

  margin-bottom: 24px;

  border: 1px solid var(--color-line);
  border-radius: var(--radius-sm);

  background: rgb(103 232 249 / 6%);
  color: var(--color-cyan);
}

.feature__icon svg {
  width: 22px;
  height: 22px;

  fill: none;
  stroke: currentColor;

  stroke-width: 1.8;
  stroke-linecap: round;
  stroke-linejoin: round;
}

.feature__title {
  margin: 0;

  font-size: 18px;
  line-height: 1.3;
}

.feature__description {
  margin: 12px 0 0;

  color: var(--color-text-muted);

  font-size: 14px;
  line-height: 1.6;
}

@media (max-width: 900px) {
  .features {
    padding-bottom: var(--space-section-tablet);
  }

  .features__grid {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}

@media (max-width: 600px) {
  .features {
    padding-bottom: var(--space-section-mobile);
  }

  .features__grid {
    grid-template-columns: 1fr;
  }

  .feature {
    padding: 24px;
  }
}
</style>
