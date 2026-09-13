<script setup lang="ts">
const analogs = [
  { name: "Аналог A", percent: 92 },
  { name: "Аналог B", percent: 87 },
  { name: "Аналог C", percent: 81 },
];
</script>

<template>
  <div class="preview card">
    <div class="preview__header">
      <span class="preview__title"> AI Model Analysis </span>

      <span class="preview__status"> Анализ выполняется </span>
    </div>

    <div class="preview__body">
      <div class="preview__model">
        <svg
          class="preview__image"
          viewBox="0 0 300 300"
          fill="none"
          aria-hidden="true"
        >
          <g stroke="#78def6" stroke-opacity=".75">
            <path d="M66 92L151 45L237 91L240 190L153 244L65 196Z" />
            <path
              d="M66 92L153 143L237 91M153 143V244M65 196L153 143L240 190"
            />
            <path d="M101 111L151 83L202 110L203 168L152 198L100 170Z" />
            <path
              d="M101 111L152 141L202 110M152 141V198M100 170L152 141L203 168"
            />
          </g>

          <g stroke="#9d7cff" stroke-opacity=".4">
            <circle cx="152" cy="143" r="110" />
            <circle cx="152" cy="143" r="78" />
            <ellipse cx="152" cy="143" rx="110" ry="42" />
          </g>
        </svg>
      </div>

      <div class="preview__analogs">
        <article
          v-for="analog in analogs"
          :key="analog.name"
          class="preview__analog card"
        >
          <div class="preview__analog-header">
            <span>{{ analog.name }}</span>
            <strong>{{ analog.percent }}%</strong>
          </div>

          <div class="preview__progress">
            <span :style="{ width: `${analog.percent}%` }" />
          </div>
        </article>
      </div>
    </div>
  </div>
</template>

<style scoped>
.preview {
  width: 100%;
  overflow: hidden;

  border-radius: var(--radius-lg);
}

.preview__header {
  display: flex;
  justify-content: space-between;
  gap: 16px;

  padding: 16px 20px;

  border-bottom: 1px solid var(--color-line);
}

.preview__title {
  font-size: 14px;
  font-weight: 600;
}

.preview__status {
  color: var(--color-green);
  font-size: 12px;
}

.preview__body {
  display: flex;
  flex-direction: column;
  gap: 16px;

  padding: 16px;
}

.preview__model {
  min-height: 360px;

  display: grid;
  place-items: center;

  border: 1px solid var(--color-line);
  border-radius: var(--radius-md);

  background: radial-gradient(circle, rgb(103 232 249 / 8%), transparent 60%);
}

.preview__image {
  width: min(60%, 260px);

  animation: model-rotate 14s linear infinite;
}

.preview__analogs {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 12px;
}

.preview__analog {
  padding: 16px;

  border-radius: var(--radius-sm);
}

.preview__analog-header {
  display: flex;
  justify-content: space-between;
  gap: 12px;

  font-size: 13px;
}

.preview__analog-header strong {
  color: var(--color-cyan);
}

.preview__progress {
  height: 4px;

  margin-top: 12px;

  overflow: hidden;

  border-radius: 999px;

  background: rgb(255 255 255 / 8%);
}

.preview__progress span {
  display: block;
  height: 100%;

  background: var(--color-cyan);
}

@keyframes model-rotate {
  to {
    transform: rotate(360deg);
  }
}

@media (max-width: 600px) {
  .preview__header {
    flex-direction: column;
  }

  .preview__model {
    min-height: 240px;
  }

  .preview__analogs {
    grid-template-columns: 1fr;
  }
}

@media (prefers-reduced-motion: reduce) {
  .preview__image {
    animation: none;
  }
}
</style>
