<template>
  <section class="support">
    <div class="container support__content">
      <div class="support__logos">
        <div class="support__logo">Логотип Фонда</div>

        <div class="support__logo">Логотип ПУТП</div>
      </div>

      <p class="support__text">
        Проект реализован при поддержке Фонда содействия инновациям в рамках
        программы «Студенческий стартап» мероприятия «Платформа университетского
        технологического предпринимательства» федерального проекта «Технологии».
      </p>
    </div>
  </section>
</template>

<style scoped>
.support {
  border-block: 1px solid var(--color-line);

  background: rgb(255 255 255 / 2%);
}

.support__content {
  display: flex;
  align-items: center;
  gap: 48px;

  padding-block: 32px;
}

.support__logos {
  display: flex;
  gap: 16px;

  flex-shrink: 0;
}

.support__logo {
  width: 140px;
  height: 64px;

  display: grid;
  place-items: center;

  border: 1px solid var(--color-line);
  border-radius: var(--radius-sm);

  color: var(--color-text-muted);

  font-size: 12px;
  text-align: center;
}

.support__text {
  max-width: 720px;

  margin: 0;

  color: var(--color-text-muted);

  font-size: 14px;
  line-height: 1.6;
}

@media (max-width: 900px) {
  .support__content {
    flex-direction: column;
    align-items: flex-start;

    gap: 24px;
  }
}

@media (max-width: 600px) {
  .support__logos {
    width: 100%;
  }

  .support__logo {
    flex: 1;
  }
}
</style>
