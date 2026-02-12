<script setup lang="ts">

</script>

<template>
  <div class="about">
    <div class="img-container">
      <img src="../assets/IMG-about.PNG" alt="" class="image">
    </div>
    <div class="right-container">
      <h1 class="title">
        Саидмурод Давлатов
      </h1>
      <h3 class="list">✦ Доктори илмҳои иқтисодӣ ва равоншиносӣ</h3>
      <h3 class="list">✦ Муаллифи силсилаасарҳои «Фалсафаи Мӯрчагон»</h3>
      <h3 class="list">✦ Бизнес-тренери дараҷаи байналмилалӣ</h3>

      <div class="goal-container">
        <p class="goal-title">Мақсади баргузорӣ:</p>
        <p class="goal-text">Барои пешрафти иқтисодиёт, дастгирии соҳибкорон ва зиёд намудани ҷойҳои корӣ.</p>
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss">
.about {
  display: flex;
  justify-content: space-between;
  width: 100%;
  padding: 0 30px;
}
.img-container {
  width: 30rem;
  height: 40rem;

  & .image {
    object-fit: cover;
    object-position: top right;
    width: 100%;
    height: 100%;
  }
}
.right-container {
  display: flex;
  flex-direction: column;

  & .title {
    color: #4f9ee5;
  }

  & .list{
    display: flex;
    margin: 10px 0;
    width: auto;
  }

  & .goal-container {
    display: flex;
    flex-direction: column;
    padding: 0 20px;
    box-shadow: rgba(43, 43, 43, 0.2) 0 0 10px;
    border-radius: 15px;
    margin-top: 20px;

    & .goal-title {
      margin-bottom: 10px;
    }

    & .goal-text {
      margin-top: 0;
    }
  }
}
</style>