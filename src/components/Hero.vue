<script setup lang="ts">
</script>

<template>
  <section class="hero" id="hero">
    <!-- Decorative background blobs -->
    <div class="hero-blob hero-blob--1" aria-hidden="true" />
    <div class="hero-blob hero-blob--2" aria-hidden="true" />

    <div class="hero-inner">
      <!-- Left: content -->
      <div class="hero-content">

        <!-- Badge -->
        <div class="hero-badge">
          <img src="../assets/Tg-logo.png" alt="Telegram" class="hero-badge__icon" />
          <span>Бахшида ба 35-солагии Истиқлолият</span>
        </div>

        <!-- Heading -->
        <h1 class="hero-title">
          Вохӯрии Ройгон<br />
          бо Устод<br />
          <span class="hero-title__accent">Саидмурод<br />Давлатов</span>
        </h1>

        <!-- Topic card -->
        <div class="hero-topic">
          <p class="hero-topic__label">Мавзӯъ</p>
          <p class="hero-topic__text">
            Идоракунии пул ва ба озодии молиявӣ расидан
          </p>
        </div>

        <!-- Phones -->
        <div class="hero-phones">
          <a href="tel:+992880000383" class="hero-phone">
            <span class="hero-phone__icon">📞</span>
            +992 88 000 03 83
          </a>
          <a href="tel:+992929704040" class="hero-phone">
            <span class="hero-phone__icon">📞</span>
            +992 92 970 40 40
          </a>
        </div>

      </div>

      <!-- Right: photo -->
      <div class="hero-photo" aria-hidden="true">
        <div class="hero-photo__frame">
          <img src="../assets/IMG_hero.PNG" alt="Саидмурод Давлатов" class="hero-photo__img" />
          <div class="hero-photo__overlay" />
        </div>
        <!-- floating stat card -->
        <div class="hero-stat">
          <p class="hero-stat__num">22<span>+</span></p>
          <p class="hero-stat__label">сол таҷриба</p>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
/* ── Section ─────────────────────── */
.hero {
  position: relative;
  min-height: 100svh;
  display: flex;
  align-items: center;
  padding: 100px 24px 60px;
  overflow: hidden;
}

/* ── Background blobs ────────────── */
.hero-blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(80px);
  pointer-events: none;
  z-index: 0;

  &--1 {
    width: 520px; height: 520px;
    top: -100px; right: -80px;
    background: radial-gradient(circle, rgba(36,99,168,.12), transparent 70%);
    animation: blobFloat 12s ease-in-out infinite alternate;
  }
  &--2 {
    width: 380px; height: 380px;
    bottom: -60px; left: -60px;
    background: radial-gradient(circle, rgba(201,168,76,.1), transparent 70%);
    animation: blobFloat 16s ease-in-out infinite alternate-reverse;
  }
}

@keyframes blobFloat {
  from { transform: translate(0, 0) scale(1); }
  to   { transform: translate(20px, 30px) scale(1.05); }
}

/* ── Inner layout ────────────────── */
.hero-inner {
  position: relative;
  z-index: 1;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 48px;
  align-items: center;
  width: 100%;
  max-width: 1160px;
  margin: 0 auto;

  @media (max-width: 900px) {
    grid-template-columns: 1fr;
    gap: 40px;
  }
}

/* ── Content ─────────────────────── */
.hero-content {
  display: flex;
  flex-direction: column;
  gap: 28px;
  animation: fadeUp .8s cubic-bezier(.4,0,.2,1) both;
}

/* Badge */
.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  background: rgba(201,168,76,.12);
  border: 1px solid rgba(201,168,76,.35);
  border-radius: 100px;
  padding: 7px 16px 7px 10px;
  width: fit-content;
  animation: fadeUp .8s .1s both;

  &__icon { height: 28px; width: 28px; border-radius: 50%; }
  span { font-size: 0.8rem; font-weight: 600; color: #8a6a1f; letter-spacing: .02em; text-transform: uppercase; }
}

/* Title */
.hero-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2.4rem, 5vw, 4.4rem);
  font-weight: 700;
  line-height: 1.1;
  color: #0f1923;
  animation: fadeUp .8s .15s both;

  &__accent {
    background: linear-gradient(135deg, #2463a8, #4f87d4);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
}

/* Topic card */
.hero-topic {
  background: #ffffff;
  border-radius: 14px;
  padding: 18px 22px;
  box-shadow: 0 4px 24px rgba(15,25,35,.08);
  border-left: 4px solid #c9a84c;
  animation: fadeUp .8s .2s both;
  max-width: 440px;

  &__label {
    font-size: 0.78rem;
    font-weight: 700;
    letter-spacing: .08em;
    text-transform: uppercase;
    color: #c9a84c;
    margin-bottom: 6px;
  }
  &__text {
    font-size: 1.05rem;
    font-weight: 500;
    color: #1c2b3a;
    line-height: 1.5;
    margin: 0;
  }
}

/* Phones */
.hero-phones {
  display: flex;
  flex-wrap: wrap;
  gap: 12px;
  animation: fadeUp .8s .25s both;
}

.hero-phone {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  font-size: 0.95rem;
  font-weight: 600;
  text-decoration: none;
  color: #ffffff;
  background: linear-gradient(135deg, #1a2d4a, #2463a8);
  padding: 11px 20px;
  border-radius: 12px;
  box-shadow: 0 4px 16px rgba(36,99,168,.3);
  transition: transform .18s, box-shadow .18s;

  &:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 24px rgba(36,99,168,.45);
  }

  &__icon { font-size: 1rem; }
}

/* ── Photo ───────────────────────── */
.hero-photo {
  position: relative;
  display: flex;
  justify-content: center;
  animation: fadeIn .9s .3s both;

  @media (max-width: 900px) {
    order: -1;
  }

  &__frame {
    position: relative;
    width: 100%;
    max-width: 440px;
    border-radius: 24px;
    overflow: hidden;
    box-shadow: 0 20px 60px rgba(15,25,35,.18);

    &::before {
      content: "";
      position: absolute;
      inset: 0;
      border-radius: 24px;
      border: 1px solid rgba(201,168,76,.25);
      z-index: 3;
      pointer-events: none;
    }
  }

  &__img {
    width: 100%;
    height: 560px;
    object-fit: cover;
    object-position: top center;
    display: block;

    @media (max-width: 900px) { height: 380px; }
  }

  &__overlay {
    position: absolute;
    bottom: 0; left: 0; right: 0;
    height: 45%;
    background: linear-gradient(to top, #f5f3ef, transparent);
    z-index: 2;
  }
}

/* Floating stat card */
.hero-stat {
  position: absolute;
  bottom: 30px;
  left: -20px;
  background: #fff;
  border-radius: 14px;
  padding: 14px 20px;
  box-shadow: 0 8px 30px rgba(15,25,35,.14);
  border: 1px solid rgba(201,168,76,.2);
  text-align: center;
  z-index: 10;
  animation: fadeUp .8s .5s both;

  @media (max-width: 900px) { left: 10px; bottom: 20px; }

  &__num {
    font-family: 'Playfair Display', serif;
    font-size: 2rem;
    font-weight: 800;
    color: #2463a8;
    line-height: 1;
    margin: 0 0 4px;

    span { font-size: 1.3rem; color: #c9a84c; }
  }
  &__label {
    font-size: 0.75rem;
    font-weight: 600;
    color: #6b7c93;
    letter-spacing: .04em;
    margin: 0;
  }
}

/* ── Animations ──────────────────── */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(24px); }
  to   { opacity: 1; transform: translateY(0); }
}
@keyframes fadeIn {
  from { opacity: 0; transform: scale(.97); }
  to   { opacity: 1; transform: scale(1); }
}
</style>