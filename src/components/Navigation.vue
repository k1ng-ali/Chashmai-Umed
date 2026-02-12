<script setup lang="ts">

</script>

<template>
  <div class="container">
    <div class="logo">
      <img src="../assets/chashma-ico.png" class="img">
    </div>
    <div class="navigation">
      <p class="item">Дар бораи устод</p>
      <p class="item">Чадвал</p>
      <p class="item">Сарпарастон</p>
    </div>
    <p class="submit">
      Номнавис
    </p>
  </div>
</template>

<style lang="scss" scoped>
  .container {
    position: fixed;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-direction: row;
    width: calc(100vw - 80px);
    padding: 0 20px;
    left:20px;
    top: 10px;
    max-width: 1200px;
    box-shadow: rgba(43, 43, 43, 0.2) 0 0 10px;
    backdrop-filter: blur(10px) saturate(140%); // Менее интенсивный blur
    border-radius: 10px;
    z-index: 100;
  }

  .img {
    height: 50px;
  }

  .item {
    background: rgba(255, 255, 255, 0);
    border: none;
    margin: 0 15px;
  }

  .navigation {
    display: flex;

  }

  .submit {
    background: #5F92FF;
    color: #fff;
    padding: 4px 10px;
    border-radius: 10px;
  }

</style>