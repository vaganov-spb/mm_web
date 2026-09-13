<template>
  <section class="section section--bordered">
    <div class="container">
      <div id="demo" class="demo card anchor-target">
        <div>
          <h2 class="section-title">
            Проверьте возможности платформы
            <span> на ваших 3D-моделях </span>
          </h2>

          <p class="section-description">
            Оставьте заявку на демонстрацию или обсуждение сценария
            использования цифровой платформы.
          </p>
        </div>

        <a href="mailto:example@example.com" class="button button--primary">
          Запросить демонстрацию ↗
        </a>
      </div>
    </div>
  </section>
</template>

<style scoped>
.demo {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 48px;

  padding: 48px;
}

.demo > div {
  min-width: 0;
}

.demo .section-description {
  margin-bottom: 0;
}

.demo .button {
  flex-shrink: 0;
}

@media (max-width: 900px) {
  .demo {
    flex-direction: column;
    align-items: flex-start;
  }
}

@media (max-width: 600px) {
  .demo {
    padding: 28px 24px;
  }

  .demo .button {
    width: 100%;
  }
}
</style>
