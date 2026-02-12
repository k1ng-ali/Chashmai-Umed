<script setup lang="ts">

</script>

<template>
  <section class="hero">
    <div class="container">
      <div class="text">
        <img src="../assets/Tg-logo.png" alt="" class="logo">
        <p class="istikloliat">
          БАХШИДА БА 35-СОЛАГИИ ИСТИқЛОЛИЯТ
        </p>
      </div>
      <h1 class="Title">Вохӯрии Ройгон <br> бо Устод <br> <span class="highlight">Саидмурод Давлатов</span></h1>
      <div class="topic-card">
        <p class="topic-title">
          Мавзӯъ:
        </p>
        <p class="topic-text">
          Идоракунии пул ва ба озодии молиявӣ расидан
        </p>
      </div>
      <div class="call-container">
        <h3 class="call">
          📞 +992 88 000 03 83
        </h3>
        <h3 class="call">
          📞 +992 92 970 40 40
        </h3>
      </div>
    </div>
    <div class="img-container">
      <img src="../assets/IMG_hero.PNG" alt="" class="image">
    </div>
  </section>
</template>

<style lang="scss" scoped>
.hero {
  display: flex;
  justify-content: space-between;
  width: 100%;
  margin-top: 100px;
  padding: 0 30px;
}
  .text {
    display: flex;
    align-items: center;
    color: #5F92FF;
  }
  .logo {
    width: 70px;
    margin-right: 30px;
  }
  .highlight {
    color: #5F92FF;
  }
  .topic-card {
    display: flex;
    flex-direction: column;
    box-shadow: rgba(43, 43, 43, 0.2) 0 0 10px;
    border-radius: 10px;
    padding: 0 20px;
    width: max-content;

    & .topic-title {
      color: #4f9ee5;
      margin-bottom: 10px;
    }
    & .topic-text {
      margin-bottom: 10px;
      margin-top: 0;
    }
  }
  .call-container{
    display: flex;
  }
  .call {
    background: #4f9ee5;
    color: #fff;
    display: flex;
    padding: 5px 10px;
    border-radius: 10px;
    width: max-content;
    margin: 20px 10px;
  }
  .img-container {
    width: 10rm;
    height: 10rm;
    position: relative;
    padding: 30px;

    & .image {
      object-fit: cover;
      object-position: top;
      width: 100%;
      height: 100%;
    }
    &::after {
      content: "";
      position: absolute;
      top: 30px;
      left: 30px;
      width: 400px;
      height: 600px;
      background: linear-gradient(rgba(255, 255, 255, 0),
          rgba(255, 255, 255, 0),
          #ffff);
      border-radius: 15px;
      z-index: 2;
    }

  }
</style>