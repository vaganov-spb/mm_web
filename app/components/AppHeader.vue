<script setup lang="ts">
const isMenuOpen = ref(false);

const links = [
  { label: "О платформе", href: "#about" },
  { label: "Возможности", href: "#features" },
  { label: "Как работает", href: "#how" },
  { label: "Безопасность", href: "#security" },
];

function closeMenu() {
  isMenuOpen.value = false;
}
</script>

<template>
  <header class="header">
    <div class="container header__inner">
      <a href="#" class="logo" @click="closeMenu">
        <span class="logo__mark" aria-hidden="true">
          <svg viewBox="0 0 32 32">
            <path d="M16 3 27 9.5v13L16 29 5 22.5v-13L16 3Z" />
            <path d="M5 9.5 16 16l11-6.5" />
            <path d="M16 16v13" />
          </svg>
        </span>

        <span class="logo__text"> 3D INTELLIGENCE </span>
      </a>

      <nav class="nav">
        <a
          v-for="link in links"
          :key="link.href"
          :href="link.href"
          class="nav__link"
        >
          {{ link.label }}
        </a>
      </nav>

      <div class="header__actions">
        <a href="#demo" class="button"> Демонстрация </a>

        <button
          class="burger"
          type="button"
          :aria-expanded="isMenuOpen"
          aria-label="Открыть меню"
          @click="isMenuOpen = !isMenuOpen"
        >
          <span />
          <span />
          <span />
        </button>
      </div>
    </div>

    <div v-if="isMenuOpen" class="mobile-menu">
      <div class="container mobile-menu__content">
        <a
          v-for="link in links"
          :key="link.href"
          :href="link.href"
          class="mobile-menu__link"
          @click="closeMenu"
        >
          {{ link.label }}
        </a>

        <a href="#demo" class="button button--primary" @click="closeMenu">
          Запросить демонстрацию
        </a>
      </div>
    </div>
  </header>
</template>

<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 50;

  width: 100%;

  border-bottom: 1px solid rgb(255 255 255 / 6%);

  background: rgb(7 10 18 / 82%);

  backdrop-filter: blur(14px);
}

.header__inner {
  display: flex;
  align-items: center;
  justify-content: space-between;

  height: 76px;
}

.logo {
  display: inline-flex;
  align-items: center;
  gap: 12px;

  flex-shrink: 0;

  font-weight: 700;
  letter-spacing: 0.04em;
}

.logo__mark {
  display: grid;
  place-items: center;

  width: 34px;
  height: 34px;

  flex-shrink: 0;

  border: 1px solid var(--color-line);
  border-radius: 10px;

  background: rgb(103 232 249 / 5%);
  color: var(--color-cyan);
}

.logo__mark svg {
  width: 22px;
  height: 22px;

  fill: none;
  stroke: currentColor;

  stroke-width: 1.5;
  stroke-linecap: round;
  stroke-linejoin: round;
}

.logo__text {
  font-size: 14px;
  white-space: nowrap;
}

.nav {
  display: flex;
  align-items: center;
  gap: 32px;

  margin-left: auto;
  margin-right: 40px;
}

.nav__link {
  color: var(--muted);

  font-size: 14px;

  transition: color 0.2s ease;
}

.nav__link:hover {
  color: var(--ink);
}

.header__actions {
  display: flex;
  align-items: center;
  gap: 16px;
}

.burger {
  display: none;

  width: 42px;
  height: 42px;

  padding: 0;

  border: 1px solid var(--line);
  border-radius: 10px;

  background: transparent;

  cursor: pointer;
}

.burger span {
  display: block;

  width: 18px;
  height: 2px;

  margin: 4px auto;

  border-radius: 2px;

  background: var(--ink);
}

.mobile-menu {
  border-top: 1px solid var(--line);

  background: rgb(7 10 18 / 98%);
}

.mobile-menu__content {
  display: flex;
  flex-direction: column;
  gap: 8px;

  padding: 20px 0 24px;
}

.mobile-menu__link {
  padding: 12px 0;

  color: var(--muted);

  font-size: 16px;
}

.mobile-menu__link:hover {
  color: var(--ink);
}

@media (max-width: 900px) {
  .nav {
    display: none;
  }

  .burger {
    display: block;
  }

  .header__actions > .button {
    display: none;
  }
}

@media (max-width: 480px) {
  .logo__text {
    font-size: 12px;
  }
}
</style>
