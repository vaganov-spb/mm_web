<script setup lang="ts">
const isMenuOpen = ref(false);

const links = [
  {
    label: "О платформе",
    href: "#about",
  },
  {
    label: "Возможности",
    href: "#features",
  },
  {
    label: "Как работает",
    href: "#how",
  },
  {
    label: "Безопасность",
    href: "#security",
  },
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
        <a href="#demo" class="button header__demo"> Демонстрация </a>

        <button
          class="burger"
          :class="{ 'burger--open': isMenuOpen }"
          type="button"
          :aria-expanded="isMenuOpen"
          :aria-label="isMenuOpen ? 'Закрыть меню' : 'Открыть меню'"
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

        <a
          href="#demo"
          class="button button--primary mobile-menu__demo"
          @click="closeMenu"
        >
          Запросить демонстрацию
        </a>
      </div>
    </div>
  </header>
</template>

<style scoped>
.header {
  position: fixed;
  z-index: 100;
  top: 0;
  right: 0;
  left: 0;

  height: var(--header-height);

  border-bottom: 1px solid var(--color-line);

  background: rgb(7 10 18 / 82%);
  backdrop-filter: blur(16px);
}

.header__inner {
  height: 100%;

  display: flex;
  align-items: center;
  justify-content: space-between;

  gap: 32px;
}

/* Logo */

.logo {
  display: inline-flex;
  align-items: center;

  gap: 12px;

  flex-shrink: 0;
}

.logo__mark {
  width: 34px;
  height: 34px;

  display: grid;
  place-items: center;

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
  font-weight: 800;

  letter-spacing: 0.08em;
}

/* Navigation */

.nav {
  display: flex;
  align-items: center;

  gap: 28px;

  margin-left: auto;
}

.nav__link {
  color: var(--color-text-muted);

  font-size: 14px;
  font-weight: 500;

  transition: color 0.2s ease;
}

.nav__link:hover {
  color: var(--color-text);
}

/* Actions */

.header__actions {
  display: flex;
  align-items: center;

  gap: 12px;

  flex-shrink: 0;
}

/* Burger */

.burger {
  position: relative;

  display: none;

  width: 40px;
  height: 40px;

  padding: 0;

  flex-shrink: 0;

  border: 1px solid var(--color-line);
  border-radius: 10px;

  background: rgb(255 255 255 / 5%);

  cursor: pointer;
}

.burger span {
  position: absolute;
  left: 50%;

  width: 18px;
  height: 2px;

  border-radius: 999px;

  background: var(--color-text);

  transform: translateX(-50%);

  transition:
    top 0.2s ease,
    transform 0.2s ease,
    opacity 0.2s ease;
}

.burger span:nth-child(1) {
  top: 13px;
}

.burger span:nth-child(2) {
  top: 19px;
}

.burger span:nth-child(3) {
  top: 25px;
}

/* Burger → X */

.burger--open span:nth-child(1) {
  top: 19px;

  transform: translateX(-50%) rotate(45deg);
}

.burger--open span:nth-child(2) {
  opacity: 0;
}

.burger--open span:nth-child(3) {
  top: 19px;

  transform: translateX(-50%) rotate(-45deg);
}

/* Mobile menu */

.mobile-menu {
  border-bottom: 1px solid var(--color-line);

  background: rgb(7 10 18 / 97%);
  backdrop-filter: blur(18px);
}

.mobile-menu__content {
  display: flex;
  flex-direction: column;

  gap: 8px;

  padding-top: 16px;
  padding-bottom: 24px;
}

.mobile-menu__link {
  padding: 14px 0;

  border-bottom: 1px solid var(--color-line);

  color: var(--color-text-muted);

  font-size: 16px;
  font-weight: 500;
}

.mobile-menu__link:hover {
  color: var(--color-text);
}

.mobile-menu__demo {
  margin-top: 12px;
}

/* Tablet */

@media (max-width: 900px) {
  .nav {
    display: none;
  }

  .burger {
    display: block;
  }
}

/* Mobile */

@media (max-width: 600px) {
  .header__inner {
    gap: 16px;
  }

  .logo__text {
    font-size: 11px;
    letter-spacing: 0.06em;
  }

  .logo__mark {
    width: 30px;
    height: 30px;
  }

  .logo__mark svg {
    width: 19px;
    height: 19px;
  }

  .header__demo {
    display: none;
  }

  .burger {
    width: 38px;
    height: 38px;

    border-radius: 9px;
  }

  .burger span {
    width: 17px;
  }

  .burger span:nth-child(1) {
    top: 12px;
  }

  .burger span:nth-child(2) {
    top: 18px;
  }

  .burger span:nth-child(3) {
    top: 24px;
  }

  .burger--open span:nth-child(1),
  .burger--open span:nth-child(3) {
    top: 18px;
  }
}
</style>
