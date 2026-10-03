<template>
  <section class="support">
    <div class="container support__content">
      <p class="support__text">
        Проект реализован при поддержке Фонда содействия инновациям в рамках
        программы «Студенческий стартап» мероприятия «Платформа университетского
        технологического предпринимательства» федерального проекта «Технологии».
      </p>
      <div class="support__logos" aria-label="Организации — партнеры проекта">
        <div class="support__logo">
          <img src="/fond_logo.png" alt="Фонд содействия инновациям" />
        </div>

        <div class="support__logo">
          <img
            src="/platform.png"
            alt="Платформа университетского технологического предпринимательства"
          />
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.support {
  border-block: 1px solid var(--color-line);

  background: rgb(255 255 255 / 2%);
}

.support__content {
  display: grid;
  grid-template-columns: minmax(0, 1fr) 220px;
  align-items: center;
  gap: 24px;

  padding-block: 32px;
}

.support__logos {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 10px;
}

.support__logo {
  min-width: 0;
  width: 105px;
  height: 82px;

  display: grid;
  place-items: center;

  background: #f4f6f8;
  overflow: hidden;

  border: 1px solid var(--color-line);
  border-radius: var(--radius-sm);

  color: var(--color-text-muted);

  font-size: 12px;
  text-align: center;
}

.support__logo img {
  display: block;
  width: 100%;
  height: 100%;

  object-fit: contain;
  object-position: center center;
}

.support__text {
  min-width: 0;

  color: var(--color-text-muted);

  font-size: 14px;
  line-height: 1.6;
}

@media (max-width: 740px) {
  .support__content {
    grid-template-columns: 1fr;
    gap: 12px;
  }

  .support__logos {
    grid-template-columns: repeat(2, fit-content(250px));
    gap: 12px;
  }
}
</style>
