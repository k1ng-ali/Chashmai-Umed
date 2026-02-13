<script setup lang="ts">
import Navigation from './components/Navigation.vue'
import Hero from './components/Hero.vue'
import About from './components/About.vue'
import Map from './components/Map.vue'
import Sponsors from "./components/Sponsors.vue";
</script>

<template>
  <div class="app">
    <Navigation />
    <main>
      <Hero />
      <About />
      <Map />
      <Sponsors />
    </main>
  </div>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;700;800&family=DM+Sans:ital,opsz,wght@0,9..40,300;0,9..40,400;0,9..40,500;0,9..40,600;0,9..40,700;1,9..40,400&display=swap');

.app {
  width: 100%;
  min-height: 100vh;
  background: #f5f3ef;
}

main {
  width: 100%;
}
</style>