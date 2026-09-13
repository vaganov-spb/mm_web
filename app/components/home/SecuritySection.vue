<script setup lang="ts">
const securityItems = [
  {
    title: "Разграничение доступа",
    description: "Доступ только к разрешенным пользователю объектам.",
  },
  {
    title: "Защищенная передача",
    description: "Передача файлов по защищенным сетевым протоколам.",
  },
  {
    title: "Контроль целостности",
    description: "Контрольные суммы для обнаружения изменений.",
  },
  {
    title: "Журналирование",
    description: "Фиксация операций загрузки, сравнения и изменения данных.",
  },
  {
    title: "Резервирование",
    description: "Резервное копирование моделей, признаков и результатов.",
  },
  {
    title: "Масштабируемость",
    description: "Расширение хранения и вычислительных ресурсов.",
  },
];
</script>

<template>
  <section class="section section--bordered">
    <div class="container">
      <div id="security" class="section-header anchor-target">
        <p class="section-label">Безопасность</p>

        <h2 class="section-title">
          3D-данные остаются
          <span>под контролем</span>
        </h2>
      </div>

      <div class="security">
        <div class="security__visual card">
          <div class="security__pulse">
            <svg
              class="security__shield"
              viewBox="0 0 24 24"
              aria-hidden="true"
            >
              <path
                d="M12 3l7 3v5c0 4.6-2.8 8.4-7 10-4.2-1.6-7-5.4-7-10V6l7-3z"
              />

              <path d="M9 12l2 2 4-4" />
            </svg>
          </div>

          <p class="security__visual-text">
            Защищенное хранение и обработка 3D-данных
          </p>
        </div>

        <div class="security__list">
          <article
            v-for="item in securityItems"
            :key="item.title"
            class="security__item card"
          >
            <div class="security__check">
              <svg viewBox="0 0 24 24" aria-hidden="true">
                <path d="M5 12l4 4L19 7" />
              </svg>
            </div>

            <div class="security__item-content">
              <h3 class="security__item-title">
                {{ item.title }}
              </h3>

              <p class="security__item-description">
                {{ item.description }}
              </p>
            </div>
          </article>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.security {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 56px;
}

/* Visual */

.security__visual {
  min-height: 420px;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 32px;

  padding: 48px;

  background:
    radial-gradient(circle at center, rgb(103 232 249 / 7%), transparent 50%),
    var(--color-surface);
}

/* Pulse */

.security__pulse {
  position: relative;

  width: 180px;
  height: 180px;

  display: grid;
  place-items: center;
}

.security__pulse::before,
.security__pulse::after {
  content: "";

  position: absolute;

  width: 110px;
  height: 110px;

  border: 1px solid rgb(103 232 249 / 16%);
  border-radius: 50%;

  animation: security-pulse 4s ease-out infinite;
}

.security__pulse::after {
  animation-delay: 2s;
}

/* Shield */

.security__shield {
  position: relative;
  z-index: 1;

  width: 72px;
  height: 72px;

  fill: none;
  stroke: var(--color-cyan);

  stroke-width: 1.2;
  stroke-linecap: round;
  stroke-linejoin: round;

  filter: drop-shadow(0 0 18px rgb(103 232 249 / 18%));
}

.security__visual-text {
  max-width: 280px;

  margin: 0;

  color: var(--color-text-muted);

  font-size: 14px;
  line-height: 1.6;
  text-align: center;
}

/* Security items */

.security__list {
  min-width: 0;

  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 16px;
}

.security__item {
  min-width: 0;

  display: flex;
  align-items: flex-start;
  gap: 16px;

  padding: 22px;
}

.security__item-content {
  min-width: 0;
}

.security__check {
  width: 32px;
  height: 32px;

  display: grid;
  place-items: center;

  flex-shrink: 0;

  border-radius: 9px;

  background: rgb(103 232 249 / 8%);
  color: var(--color-cyan);
}

.security__check svg {
  width: 17px;
  height: 17px;

  fill: none;
  stroke: currentColor;

  stroke-width: 2;
  stroke-linecap: round;
  stroke-linejoin: round;
}

.security__item-title {
  margin: 3px 0 0;

  font-size: 15px;
  line-height: 1.4;
}

.security__item-description {
  margin: 8px 0 0;

  color: var(--color-text-muted);

  font-size: 13px;
  line-height: 1.55;
}

/* Animation */

@keyframes security-pulse {
  0% {
    opacity: 0;
    transform: scale(0.75);
  }

  15% {
    opacity: 0.65;
  }

  100% {
    opacity: 0;
    transform: scale(1.6);
  }
}

/* Intermediate */

@media (max-width: 1100px) {
  .security {
    gap: 32px;
  }

  .security__list {
    grid-template-columns: 1fr;
  }
}

/* Tablet */

@media (max-width: 900px) {
  .security {
    grid-template-columns: 1fr;
    gap: 24px;
  }

  .security__visual {
    min-height: 300px;
  }

  .security__list {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}

/* Mobile */

@media (max-width: 600px) {
  .security__visual {
    min-height: 260px;
    padding: 32px 24px;
  }

  .security__pulse {
    width: 140px;
    height: 140px;
  }

  .security__shield {
    width: 60px;
    height: 60px;
  }

  .security__list {
    grid-template-columns: 1fr;
  }

  .security__item {
    padding: 20px;
  }
}

/* Accessibility */

@media (prefers-reduced-motion: reduce) {
  .security__pulse::before,
  .security__pulse::after {
    animation: none;
  }
}
</style>
