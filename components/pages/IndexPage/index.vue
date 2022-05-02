<template>
  <div class="container">
    <div class="title">Главная страница</div>
    <div class="subtitle">Является обзорной страницей с приветствием и восхвалением создателя</div>
    <div class="subtitle">Приветсвуйте и восхваляйте!</div>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'

  export default Vue.extend({
    
  })
</script>

<style scoped>
  .container {
    padding: 20px;
    font-size: 32px;
  }
  .title  {
    font-size: 36px;
    display: flex;
    justify-content: center;
  }
  .subtitle  {
    font-size: 24px;
    display: flex;
    justify-content: center;
    margin-top: 50px;
  }
</style>