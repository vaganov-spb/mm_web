<template>
  <footer class="footer">
    <div class="container footer__content">
      <div>
        <strong class="footer__brand"> 3D INTELLIGENCE </strong>

        <p class="footer__text">
          Цифровая платформа интеллектуального сравнения 3D-моделей
        </p>
      </div>

      <div class="footer__meta">
        Проект № 106787
        <br />
        © 2026 [Название юридического лица]
      </div>
    </div>
  </footer>
</template>

<style scoped>
.footer {
  border-top: 1px solid var(--color-line);
}

.footer__content {
  display: flex;
  justify-content: space-between;
  gap: 40px;

  padding-block: 40px;
}

.footer__brand {
  font-size: 14px;
  letter-spacing: 0.04em;
}

.footer__text {
  max-width: 480px;

  margin: 10px 0 0;

  color: var(--color-text-muted);

  font-size: 14px;
  line-height: 1.6;
}

.footer__meta {
  color: var(--color-text-muted);

  font-size: 13px;
  line-height: 1.7;
  text-align: right;
}

@media (max-width: 600px) {
  .footer__content {
    flex-direction: column;
  }

  .footer__meta {
    text-align: left;
  }
}
</style>
