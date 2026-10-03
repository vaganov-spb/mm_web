<script setup lang="ts">
const steps = [
  { number: "01", title: "Загрузка 3D-модели", description: "Пользователь загружает трехмерную модель через интерфейс платформы. Для каждого объекта создается отдельная задача обработки и фиксируются основные параметры загрузки." },
  { number: "02", title: "Проверка файла", description: "Система проверяет корректность формата, структуру модели и наличие геометрических данных. Дополнительно вычисляется контрольная сумма для выявления ранее обработанных объектов." },
  { number: "03", title: "Нормализация геометрии", description: "Модель приводится к единому внутреннему представлению. Система уменьшает влияние масштаба, положения и ориентации объекта на дальнейшее сравнение." },
  { number: "04", title: "Поиск аналогов", description: "По сформированным признакам система выполняет поиск наиболее близких моделей в базе данных. Для ускорения поиска используется индексированное признаковое пространство." },
  { number: "05", title: "Сравнение и ранжирование", description: "Найденные кандидаты проходят дополнительный сравнительный анализ. После этого модели ранжируются по рассчитанной степени сходства." },
  { number: "06", title: "Результат анализа", description: "Пользователь получает упорядоченный перечень ближайших аналогов и результаты сравнительного анализа. Полученные данные сохраняются в платформе для дальнейшего использования." },
];
</script>

<template>
  <section class="section section--bordered">
    <div class="container">
      <div id="how" class="section-header anchor-target">
        <p class="section-label">Как это работает</p>

        <h2 class="section-title">
          От загрузки модели —
          <span> к результату анализа </span>
        </h2>

        <p class="section-description">
          Пользователь загружает 3D-модель, после чего платформа автоматически
          проверяет и нормализует объект. Далее система формирует его цифровое
          признаковое представление и выполняет интеллектуальный поиск
          ближайших аналогов. Найденные модели сравниваются и ранжируются по
          степени сходства.
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

          <p class="pipeline__description">
            {{ step.description }}
          </p>
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
  min-height: 300px;

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

.pipeline__description {
  margin: 16px 0 0;

  color: var(--color-text-muted);

  font-size: 13px;
  line-height: 1.55;
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
