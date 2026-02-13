<script setup lang="ts">
const achievements = [
  { icon: '🎓', text: 'Доктори илмҳои иқтисодӣ ва равоншиносӣ' },
  { icon: '📚', text: 'Муаллифи силсилаасарҳои «Фалсафаи Мӯрчагон»' },
  { icon: '🌍', text: 'Бизнес-тренери дараҷаи байналмилалӣ' },
]
</script>

<template>
  <section class="about" id="about">
    <!-- Decorative line -->
    <div class="about-blob" aria-hidden="true" />

    <div class="about-inner">
      <!-- Photo column -->
      <div class="about-photo">
        <div class="about-photo__frame">
          <img src="../assets/IMG-about.PNG" alt="Саидмурод Давлатов" class="about-photo__img" />
        </div>
        <!-- experience badge -->
        <div class="about-badge">
          <span class="about-badge__line1">Бизнес-тренер</span>
          <span class="about-badge__line2">дараҷаи №1</span>
        </div>
      </div>

      <!-- Text column -->
      <div class="about-content">
        <p class="about-eyebrow">Дар бораи устод</p>

        <h2 class="about-title">Саидмурод<br /><span class="about-title__accent">Давлатов</span></h2>

        <!-- Achievement list -->
        <ul class="about-list">
          <li
              v-for="(item, i) in achievements"
              :key="i"
              class="about-list__item"
              :style="{ animationDelay: `${0.1 + i * 0.1}s` }"
          >
            <span class="about-list__icon">{{ item.icon }}</span>
            <span class="about-list__text">{{ item.text }}</span>
          </li>
        </ul>

        <!-- Goal card -->
        <div class="about-goal">
          <div class="about-goal__header">
            <div class="about-goal__dot" />
            <p class="about-goal__title">Мақсади баргузорӣ</p>
          </div>
          <p class="about-goal__text">
            Барои пешрафти иқтисодиёт, дастгирии соҳибкорон
            ва зиёд намудани ҷойҳои корӣ.
          </p>
        </div>

        <!-- CTA -->
        <a href="https://docs.google.com/forms/d/e/1FAIpQLScVjwW0fhKGgRBvut-FeyhsAWvDORtB30pejSgExLyRp2NOMg/viewform" class="about-cta">
          Ба вохӯрӣ номнавис шавед
          <span class="about-cta__arrow">→</span>
        </a>
      </div>
    </div>
  </section>
</template>

<style lang="scss" scoped>
/* ── Section ─────────────────────── */
.about {
  position: relative;
  padding: 80px 24px;
  overflow: hidden;
}

.about-blob {
  position: absolute;
  width: 600px; height: 600px;
  top: 50%; right: -150px;
  transform: translateY(-50%);
  border-radius: 50%;
  background: radial-gradient(circle, rgba(36,99,168,.07), transparent 68%);
  filter: blur(60px);
  pointer-events: none;
}

/* ── Inner grid ──────────────────── */
.about-inner {
  max-width: 1160px;
  margin: 0 auto;
  display: grid;
  grid-template-columns: 480px 1fr;
  gap: 64px;
  align-items: center;

  @media (max-width: 960px) {
    grid-template-columns: 1fr;
    gap: 40px;
  }
}

/* ── Photo ───────────────────────── */
.about-photo {
  position: relative;

  &__frame {
    border-radius: 24px;
    overflow: hidden;
    box-shadow: 0 20px 60px rgba(15,25,35,.15);
    border: 1px solid rgba(201,168,76,.2);
  }

  &__img {
    width: 100%;
    height: 520px;
    object-fit: cover;
    object-position: top right;
    display: block;

    @media (max-width: 960px) { height: 340px; }
  }
}

/* Badge floating */
.about-badge {
  position: absolute;
  top: 24px;
  right: -16px;
  background: linear-gradient(135deg, #1a2d4a, #2463a8);
  border-radius: 14px;
  padding: 14px 18px;
  color: #fff;
  box-shadow: 0 8px 28px rgba(36,99,168,.35);
  text-align: center;

  @media (max-width: 960px) { right: 12px; top: 16px; }

  &__line1 { display: block; font-size: 0.75rem; font-weight: 500; opacity: .8; }
  &__line2 {
    display: block;
    font-family: 'Playfair Display', serif;
    font-size: 1.1rem;
    font-weight: 700;
    color: #e8c97a;
    margin-top: 2px;
  }
}

/* ── Content ─────────────────────── */
.about-content {
  display: flex;
  flex-direction: column;
  gap: 24px;
  animation: fadeUp .8s .1s both;
}

.about-eyebrow {
  font-size: 0.78rem;
  font-weight: 700;
  letter-spacing: .1em;
  text-transform: uppercase;
  color: #c9a84c;
  margin: 0;
}

.about-title {
  font-family: 'Playfair Display', serif;
  font-size: clamp(2rem, 4vw, 3.2rem);
  font-weight: 700;
  line-height: 1.1;
  color: #0f1923;
  margin: 0;

  &__accent {
    background: linear-gradient(135deg, #2463a8, #4f87d4);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
}

/* Achievements */
.about-list {
  list-style: none;
  display: flex;
  flex-direction: column;
  gap: 12px;

  &__item {
    display: flex;
    align-items: center;
    gap: 14px;
    background: #fff;
    border-radius: 12px;
    padding: 14px 18px;
    box-shadow: 0 2px 14px rgba(15,25,35,.07);
    border: 1px solid rgba(201,168,76,.1);
    animation: fadeUp .7s both;
    transition: transform .18s, box-shadow .18s;

    &:hover {
      transform: translateX(4px);
      box-shadow: 0 4px 20px rgba(36,99,168,.12);
    }
  }

  &__icon {
    font-size: 1.3rem;
    flex-shrink: 0;
    width: 36px; height: 36px;
    display: flex; align-items: center; justify-content: center;
    background: rgba(201,168,76,.1);
    border-radius: 8px;
  }

  &__text {
    font-size: 0.97rem;
    font-weight: 500;
    color: #1c2b3a;
    line-height: 1.4;
  }
}

/* Goal card */
.about-goal {
  background: linear-gradient(135deg, #0f1923, #1a2d4a);
  border-radius: 16px;
  padding: 22px 24px;
  color: #fff;
  box-shadow: 0 8px 30px rgba(15,25,35,.18);

  &__header {
    display: flex;
    align-items: center;
    gap: 10px;
    margin-bottom: 12px;
  }

  &__dot {
    width: 8px; height: 8px;
    border-radius: 50%;
    background: #c9a84c;
    box-shadow: 0 0 8px rgba(201,168,76,.6);
  }

  &__title {
    font-size: 0.78rem;
    font-weight: 700;
    letter-spacing: .08em;
    text-transform: uppercase;
    color: #e8c97a;
    margin: 0;
  }

  &__text {
    font-size: 0.97rem;
    color: rgba(255,255,255,.85);
    line-height: 1.6;
    margin: 0;
  }
}

/* CTA */
.about-cta {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  font-size: 0.95rem;
  font-weight: 700;
  text-decoration: none;
  color: #0f1923;
  background: linear-gradient(135deg, #e8c97a, #c9a84c);
  padding: 14px 26px;
  border-radius: 12px;
  width: fit-content;
  box-shadow: 0 4px 20px rgba(201,168,76,.35);
  transition: transform .18s, box-shadow .18s;

  &:hover {
    transform: translateY(-2px);
    box-shadow: 0 6px 28px rgba(201,168,76,.5);
  }

  &__arrow {
    font-size: 1.1rem;
    transition: transform .18s;
  }
  &:hover &__arrow { transform: translateX(4px); }
}

@keyframes fadeUp {
  from { opacity: 0; transform: translateY(20px); }
  to   { opacity: 1; transform: translateY(0); }
}
</style>