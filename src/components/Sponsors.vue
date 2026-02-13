<script setup lang="ts">
</script>

<template>
  <section class="sponsors" id="sponsors">
    <div class="blob blob--1" aria-hidden="true" />
    <div class="blob blob--2" aria-hidden="true" />

    <div class="sponsors-inner">

      <!-- Header -->
      <div class="sponsors-header">
        <p class="eyebrow">Дастгирикунандагон</p>
        <h2 class="sponsors-title">Сарпарастон ва ҳамкорон</h2>
      </div>

      <!-- Logo grid -->
      <div class="sponsors-grid">
        <a href="https://worldsamo.com/"
            class="sponsor-card samo"
        >
          <img src="../assets/Samo.png" alt="САМО" class="sponsor-card__img" />
        </a>
        <a href="https://newradio.tj/"
            class="sponsor-card nav"
        >
          <img src="../assets/RadioNav.png" alt="RadioNav" class="sponsor-card__img" />
        </a>
        <a href="https://it-tajikistan.dcn.tj/"
            class="sponsor-card it"
        >
          <img src="../assets/ItTj.png" alt="It-Tajikistan" class="sponsor-card__img it-tj" />
        </a>
      </div>

    </div>
  </section>

  <!-- Footer -->
  <footer class="footer">
    <div class="footer-inner">

      <!-- Left: logo + copy -->
      <div class="footer-left">
        <img src="../assets/chashma-ico.png" alt="Чашмаи Умед" class="footer-logo" />
        <p class="footer-copy">© 2025 Чашмаи Умед. Ҳамаи ҳуқуқҳо ҳифз шудаанд.</p>
      </div>

      <!-- Right: phones -->
      <div class="footer-phones">
        <a href="tel:+992880000383" class="footer-phone">
          <span class="footer-phone__icon">📞</span>
          +992 88 0000 383
        </a>
        <a href="tel:+992929704040" class="footer-phone">
          <span class="footer-phone__icon">📞</span>
          +992 92 970 40 40
        </a>
      </div>

    </div>
  </footer>
</template>

<style lang="scss" scoped>
/* ── Sponsors Section ────────────── */
.sponsors {
  position: relative;
  padding: 80px 24px 96px;
  overflow: hidden;
}

.blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(90px);
  pointer-events: none;
  &--1 {
    width: 460px; height: 460px;
    top: -60px; right: -80px;
    background: radial-gradient(circle, rgba(201,168,76,.09), transparent 70%);
  }
  &--2 {
    width: 360px; height: 360px;
    bottom: 0; left: -60px;
    background: radial-gradient(circle, rgba(36,99,168,.07), transparent 70%);
  }
}

.sponsors-inner {
  max-width: 1160px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 52px;
}

/* Header */
.sponsors-header { text-align: center; }

.eyebrow {
  font-size: .78rem;
  font-weight: 700;
  letter-spacing: .1em;
  text-transform: uppercase;
  color: #c9a84c;
  margin: 0 0 10px;
}

.sponsors-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(1.9rem, 4vw, 3rem);
  font-weight: 700;
  color: #0f1923;
  margin: 0;
}

/* Grid */
.sponsors-grid {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 24px;
  width: 100%;
}

.sponsor-card {
  display: flex;
  align-items: center;
  justify-content: center;
  width: calc(33.33% - 16px);
  min-width: 200px;
  max-width: 320px;
  aspect-ratio: 16 / 9;
  background: #ffffff;
  border-radius: 18px;
  border: 1px solid rgba(201,168,76,.18);
  box-shadow: 0 4px 24px rgba(15,25,35,.07);
  padding: 28px 36px;
  transition: transform .22s ease, box-shadow .22s ease, border-color .22s ease;
  cursor: default;

  &:hover {
    transform: translateY(-4px);
    box-shadow: 0 12px 40px rgba(15,25,35,.12);
    border-color: rgba(201,168,76,.4);
  }

  &__img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    filter: grayscale(20%);
    transition: filter .22s;
  }

  &.nav {
    padding: 10px;
  }
  &.it {
    padding: 0;
    overflow: hidden;

    &__img {
      scale: 1.2;
    }
  }

  &:hover &__img {
    filter: grayscale(0%);
  }

  @media (max-width: 640px) {
    width: calc(50% - 12px);
    min-width: 140px;
    padding: 20px 24px;
  }
  @media (max-width: 400px) {
    width: 100%;
    max-width: 100%;
  }
}

/* ── Footer ──────────────────────── */
.footer {
  background: #0f1923;
  border-top: 1px solid rgba(201,168,76,.15);
}

.footer-inner {
  max-width: 1160px;
  margin: 0 auto;
  padding: 28px 24px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 20px;

  @media (max-width: 640px) {
    flex-direction: column;
    align-items: flex-start;
    gap: 16px;
  }
}

/* Left */
.footer-left {
  display: flex;
  align-items: center;
  gap: 14px;
  flex-wrap: wrap;
}

.footer-logo {
  height: 36px;
  width: auto;
  opacity: .9;
}

.footer-copy {
  font-size: .85rem;
  color: rgba(255,255,255,.45);
  margin: 0;
  line-height: 1.4;
}

/* Phones */
.footer-phones {
  display: flex;
  gap: 16px;
  flex-wrap: wrap;

  @media (max-width: 640px) { gap: 10px; }
}

.footer-phone {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  font-size: .9rem;
  font-weight: 600;
  text-decoration: none;
  color: #c9a84c;
  transition: color .18s;

  &:hover { color: #e8c97a; }

  &__icon { font-size: .85rem; opacity: .8; }
}
</style>