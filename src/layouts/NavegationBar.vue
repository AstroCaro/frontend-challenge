<template>
  <header>
    <div class="header-mobile" :class="{ open: menuMobile }">
      <div class="mobile-menu-close">
        <a @click="menuMobile = false">
          <span class="material-symbols-outlined"> close </span>
        </a>
      </div>
      <div class="mobile-menu-nav-bar">
        <div class="nav-link" v-for="link in essentialLinks" :key="link.title">
          <RouterLink :to="link.to">{{ formatTitle(link.title) }}</RouterLink>
          <span class="nav-expand-icon material-symbols-outlined">
            keyboard_arrow_down
          </span>
        </div>
        <div>
          <div class="nav-link nav-shop-cart">
            <span class="material-symbols-outlined">shopping_cart </span>
            <span>Cart (3)</span>
          </div>
        </div>
        <div class="nav-link">
          <v-button label="Sign In" icon="person" background="#39e29d" color="#373636" />
        </div>
      </div>
    </div>
    <div class="header-desktop">
      <div class="hamburguer-menu">
        <a target="_blank" rel="noopener noreferrer" @click="menuMobile = true">
          <span class="material-symbols-outlined"> menu </span>
        </a>
      </div>
      <div class="nav-logo">
        <img src="../assets/logos/chicks-logo-large.svg" alt="Chicks Gold's Logo" />
      </div>
      <nav class="nav-bar">
        <div class="nav-link" v-for="link in essentialLinks" :key="link.title">
          <RouterLink :to="link.to">{{ formatTitle(link.title) }}</RouterLink>
          <span class="nav-expand-icon material-symbols-outlined">
            keyboard_arrow_down
          </span>
        </div>
      </nav>
      <div class="nav-account">
        <div class="nav-link">
          <div>usd</div>
          <span class="nav-expand-icon material-symbols-outlined">
            keyboard_arrow_down
          </span>
        </div>
        <div class="nav-link nav-shop-cart">
          <span class="material-symbols-outlined">shopping_cart </span>
          <span>Cart (3)</span>
        </div>
        <v-button label="Sign In" icon="person" background="#39e29d" color="#373636" />
      </div>
    </div>
  </header>
</template>

<script setup>
import { RouterLink } from 'vue-router';
import VButton from '@/components/VButton.vue';
import { ref } from 'vue';

const menuMobile = ref(false);

const essentialLinks = [
  {
    title: 'Currency',
    to: '#/',
  },
  {
    title: 'Items',
    to: '#/',
  },
  {
    title: 'Accounts',
    to: '#/',
  },
  {
    title: 'Services',
    to: '#/',
  },
  {
    title: 'Swap',
    to: '#/',
  },
  {
    title: 'Sell',
    to: '#/',
  },
];

const formatTitle = (title) => {
  return title.toUpperCase();
};
</script>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
  width: 100%;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1001;
}

.header-mobile {
  position: absolute;
  background-color: var(--color-background);
  width: 100vw;
  height: 100vh;
  left: 0;
  top: 0;
  opacity: 0;
  margin-left: -100vw;
  padding: 50px;
  transition: margin-left 0.2s, opacity 0.2s;
}

.header-mobile.open {
  opacity: 1;
  margin-left: 0px;
}

.mobile-menu-nav-bar {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding: 20px 0px;
  gap: 40px;
}

.header-mobile a {
  color: white;
}

.menu-mobile-close {
  border-bottom: solid 1px red;
}

.header-desktop {
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 0 auto;
  padding: 12px;
  background: #303141;
  border-bottom: 1px solid rgba(76, 96, 133, 0.5);
  min-height: 72px;
  padding-bottom: 0 !important;
  padding-top: 0 !important;
  transition: background-color 0.5s ease;
}

nav {
  width: 100%;
  display: flex;
  font-size: 14px;
  letter-spacing: 0.68px;
  padding-left: 10px;
  flex: 1;
  gap: 30px;
}

.nav-logo img {
  max-width: 160px;
  margin-bottom: 1rem;
}

.nav-logo {
  border-right: 1px solid hsla(0, 0%, 100%, 0.3);
  padding: 0 40px 0 20px;
  margin-right: 0.5rem !important;
  display: none;
}

.nav-link {
  display: flex;
  align-items: center;
  text-transform: uppercase;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a:first-of-type {
  border: 0;
}

.nav-expand-icon {
  font-weight: 300;
}

.nav-account {
  display: flex;
  font-size: 14px;
  letter-spacing: 0.68px;
  padding-left: 40px;
  gap: 20px;
}

.hamburguer-menu {
  display: block;
}

.hamburguer-menu a {
  color: white;
}

.nav-bar {
  display: none;
}

.nav-account {
  display: none;
}

@media (min-width: 768px) {
  .nav-logo {
    display: none;
  }

  .hamburguer-menu {
    display: block;
  }
  .nav-account {
    display: flex;
  }
}

@media (min-width: 1024px) {
  .hamburguer-menu {
    display: none;
  }

  nav {
    display: flex;
    font-size: 14px;
    letter-spacing: 0.68px;
    margin-left: 10px;
    flex: 1;
    gap: 30px;
  }

  .nav-bar {
    display: flex;
  }
}

@media (min-width: 1280px) {
  .hamburguer-menu {
    display: none;
  }
  .nav-logo {
    display: block;
  }

  .nav-bar {
    display: flex;
  }
}
</style>
