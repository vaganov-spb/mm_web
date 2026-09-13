<script setup lang="ts">
const steps = [
  { number: "01", title: "Загрузка 3D-модели" },
  { number: "02", title: "Проверка файла" },
  { number: "03", title: "Нормализация геометрии" },
  { number: "04", title: "ИИ-анализ признаков" },
  { number: "05", title: "Поиск аналогов" },
  { number: "06", title: "Сравнение и ранжирование" },
  { number: "07", title: "Результат анализа" },
];
</script>

<template>
  <section class="section section--bordered">
    <div class="container">
      <div id="how" class="section-header anchor-target">
        <p class="section-label">Как это работает</p>

        <h2 class="section-title">
          Семь этапов.
          <span> Один автоматизированный процесс. </span>
        </h2>

        <p class="section-description">
          Пользователь загружает модель — дальше платформа последовательно
          выполняет подготовку, интеллектуальную обработку и формирование
          результата.
        </p>
      </div>

      <div class="pipeline">
        <article
          v-for="step in steps"
          :key="step.number"
          class="pipeline__item card"
        >
          <span class="pipeline__number">
            {{ step.number }}
          </span>

          <h3 class="pipeline__title">
            {{ step.title }}
          </h3>
        </article>
      </div>
    </div>
  </section>
</template>

<style scoped>
.pipeline {
  display: grid;

  grid-template-columns: repeat(4, minmax(0, 1fr));

  gap: 16px;
}

.pipeline__item {
  min-height: 160px;

  display: flex;
  flex-direction: column;
  justify-content: space-between;

  padding: 24px;
}

.pipeline__number {
  color: var(--color-cyan);

  font-size: 13px;
  font-weight: 700;
  letter-spacing: 0.08em;
}

.pipeline__title {
  max-width: 180px;

  margin: 32px 0 0;

  font-size: 17px;
  line-height: 1.4;
}

@media (max-width: 900px) {
  .pipeline {
    grid-template-columns: repeat(2, minmax(0, 1fr));
  }
}

@media (max-width: 600px) {
  .pipeline {
    grid-template-columns: 1fr;
  }
}
</style>
