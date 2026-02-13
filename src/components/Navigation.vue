<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const menuOpen   = ref(false)
const scrolled   = ref(false)

function onScroll() { scrolled.value = window.scrollY > 30 }
onMounted(()  => window.addEventListener('scroll', onScroll))
onUnmounted(() => window.removeEventListener('scroll', onScroll))
</script>

<template>
  <header :class="['nav-wrap', { scrolled }]">
    <nav class="nav">

      <!-- Logo -->
      <a href="#" class="nav-logo" aria-label="На главную">
        <img src="../assets/chashma-ico.png" alt="Логотип" class="nav-logo__img" />
      </a>

      <!-- Desktop links -->
      <ul class="nav-links">
        <li><a href="#about"   class="nav-link">Дар бораи устод</a></li>
        <li><a href="#schedule" class="nav-link">Чадвал</a></li>
        <li><a href="#sponsors" class="nav-link">Сарпарастон</a></li>
      </ul>

      <!-- CTA -->
      <a href="https://docs.google.com/forms/d/e/1FAIpQLScVjwW0fhKGgRBvut-FeyhsAWvDORtB30pejSgExLyRp2NOMg/viewform" class="nav-cta">Номнавис</a>

      <!-- Burger -->
      <button
          class="nav-burger"
          :class="{ open: menuOpen }"
          @click="menuOpen = !menuOpen"
          aria-label="Меню"
      >
        <span /><span /><span />
      </button>
    </nav>

    <!-- Mobile drawer -->
    <div class="nav-drawer" :class="{ open: menuOpen }">
      <a href="#about"    class="drawer-link" @click="menuOpen=false">Дар бораи устод</a>
      <a href="#schedule" class="drawer-link" @click="menuOpen=false">Чадвал</a>
      <a href="#sponsors" class="drawer-link" @click="menuOpen=false">Сарпарастон</a>
      <a href="#register" class="drawer-cta"  @click="menuOpen=false">Номнавис</a>
    </div>
  </header>
</template>

<style lang="scss" scoped>
/* ── Wrapper ─────────────────────── */
.nav-wrap {
  position: fixed;
  top: 12px;
  left: 50%;
  transform: translateX(-50%);
  width: calc(100% - 32px);
  max-width: 1160px;
  z-index: 200;
  transition: top .3s ease, box-shadow .3s ease;

  &.scrolled {
    top: 8px;
    .nav {
      background: rgba(255, 252, 245, 0.5);
      box-shadow: 0 4px 32px rgba(15,25,35,.14);
    }
  }
}

/* ── Bar ─────────────────────────── */
.nav {
  display: flex;
  align-items: center;
  padding: 0 20px;
  height: 62px;
  background: rgba(255,252,245,.72);
  backdrop-filter: blur(14px) saturate(160%);
  -webkit-backdrop-filter: blur(14px) saturate(160%);
  border-radius: 16px;
  border: 1px solid rgba(201,168,76,.22);
  transition: background .3s, box-shadow .3s;
}

/* ── Logo ────────────────────────── */
.nav-logo {
  display: flex;
  align-items: center;
  flex-shrink: 0;
  &__img { height: 40px; width: auto; }
}

/* ── Desktop links ───────────────── */
.nav-links {
  display: flex;
  list-style: none;
  gap: 4px;
  margin: 0 auto;

  @media (max-width: 768px) { display: none; }
}

.nav-link {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.92rem;
  font-weight: 500;
  color: #1c2b3a;
  text-decoration: none;
  padding: 6px 14px;
  border-radius: 8px;
  transition: background .18s, color .18s;

  &:hover {
    background: rgba(36,99,168,.08);
    color: #2463a8;
  }
}

/* ── CTA ─────────────────────────── */
.nav-cta {
  font-family: 'DM Sans', sans-serif;
  font-size: 0.9rem;
  font-weight: 600;
  text-decoration: none;
  color: #0f1923;
  background: linear-gradient(135deg, #e8c97a, #c9a84c);
  padding: 8px 20px;
  border-radius: 10px;
  white-space: nowrap;
  box-shadow: 0 2px 12px rgba(201,168,76,.35);
  transition: transform .18s, box-shadow .18s;
  flex-shrink: 0;
  margin-left: 12px;

  &:hover {
    transform: translateY(-1px);
    box-shadow: 0 4px 20px rgba(201,168,76,.5);
  }

  @media (max-width: 768px) { display: none; }
}

/* ── Burger ──────────────────────── */
.nav-burger {
  display: none;
  flex-direction: column;
  justify-content: space-between;
  width: 24px;
  height: 17px;
  background: none;
  border: none;
  cursor: pointer;
  margin-left: auto;
  padding: 0;

  span {
    display: block;
    height: 2px;
    background: #1c2b3a;
    border-radius: 2px;
    transition: transform .25s ease, opacity .25s ease, width .25s ease;
    transform-origin: left center;
  }

  &.open span:nth-child(1) { transform: rotate(45deg) translate(0px, -1px); }
  &.open span:nth-child(2) { opacity: 0; transform: scaleX(0); }
  &.open span:nth-child(3) { transform: rotate(-45deg) translate(0px, 1px); }

  @media (max-width: 768px) { display: flex; }
}

/* ── Mobile Drawer ───────────────── */
.nav-drawer {
  display: flex;
  flex-direction: column;
  overflow: hidden;
  max-height: 0;
  opacity: 0;
  transition: max-height .35s cubic-bezier(.4,0,.2,1), opacity .3s ease, padding .3s ease;
  background: rgba(255,252,245,.97);
  backdrop-filter: blur(14px);
  border-radius: 0 0 16px 16px;
  border: 1px solid rgba(201,168,76,.18);
  border-top: none;

  &.open {
    max-height: 320px;
    opacity: 1;
    padding: 16px 20px 20px;
  }
}

.drawer-link {
  font-family: 'DM Sans', sans-serif;
  font-size: 1rem;
  font-weight: 500;
  color: #1c2b3a;
  text-decoration: none;
  padding: 12px 0;
  border-bottom: 1px solid rgba(201,168,76,.15);
  transition: color .15s;

  &:last-of-type { border-bottom: none; }
  &:hover { color: #2463a8; }
}

.drawer-cta {
  margin-top: 14px;
  font-family: 'DM Sans', sans-serif;
  font-size: 0.95rem;
  font-weight: 700;
  text-decoration: none;
  color: #0f1923;
  background: linear-gradient(135deg, #e8c97a, #c9a84c);
  padding: 12px 20px;
  border-radius: 10px;
  text-align: center;
  box-shadow: 0 2px 12px rgba(201,168,76,.35);
}
</style>