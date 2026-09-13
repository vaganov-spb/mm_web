<template>
  <section class="hero">
    <div class="container hero__content">
      <div class="hero__info">
        <div class="hero__badge">
          <span class="hero__badge-dot" />
          AI × 3D Engineering
        </div>

        <h1 class="hero-title hero__title">
          Интеллектуальное сравнение

          <span class="hero__accent"> 3D-моделей </span>
        </h1>

        <p class="hero__description">
          Цифровая платформа для загрузки, нормализации, интеллектуального
          анализа, поиска ближайших аналогов и безопасного хранения трехмерных
          моделей.
        </p>

        <div class="hero__actions">
          <a href="#demo" class="button button--primary">
            Запросить демонстрацию
          </a>

          <a href="#how" class="button"> Как это работает </a>
        </div>

        <p class="hero__meta">
          Проект № 106787 · программа «Студенческий стартап»
        </p>
      </div>

      <HeroModelPreview />
    </div>
  </section>
</template>

<style scoped>
.hero {
  padding: 140px 0 100px;
}

.hero__content {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  align-items: center;
  gap: clamp(48px, 7vw, 96px);
}

.hero__info {
  min-width: 0;
}

.hero__badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;

  padding: 8px 12px;

  border: 1px solid var(--color-line);
  border-radius: 999px;

  background: rgb(255 255 255 / 4%);
  color: var(--color-text-muted);

  font-size: 13px;
  font-weight: 600;
  text-transform: uppercase;
}

.hero__badge-dot {
  width: 8px;
  height: 8px;

  flex-shrink: 0;

  border-radius: 50%;
  background: var(--color-green);
}

.hero__title {
  margin-top: 24px;
}

.hero__accent {
  display: block;

  background: linear-gradient(
    90deg,
    var(--color-text),
    var(--color-cyan),
    var(--color-violet)
  );

  background-clip: text;
  -webkit-background-clip: text;

  color: transparent;
}

.hero__description {
  max-width: 620px;

  margin: 20px 0 0;

  color: var(--color-text-muted);

  font-size: var(--font-size-body);
  line-height: 1.6;
}

.hero__actions {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;

  margin-top: 32px;
}

.hero__meta {
  margin: 20px 0 0;

  color: #74809b;
  font-size: 13px;
}

@media (max-width: 900px) {
  .hero {
    padding: 120px 0 var(--space-section-tablet);
  }

  .hero__content {
    grid-template-columns: 1fr;
    gap: 56px;
  }
}

@media (max-width: 600px) {
  .hero {
    padding: 104px 0 var(--space-section-mobile);
  }

  .hero__description {
    font-size: var(--font-size-body-mobile);
  }

  .hero__actions {
    flex-direction: column;
  }

  .hero__actions .button {
    width: 100%;
  }
}
</style>
