<template>
  <div class="header">
    <nuxt-link class="link" to="/">На главную</nuxt-link>
    <nuxt-link class="link" to="/calculators">Калькуляторы</nuxt-link>
    <nuxt-link class="link" to="/design">Вёрстка</nuxt-link>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'

  export default Vue.extend({
    
  })
</script>

<style scoped>
.header {
  height: 50px;
  background-color:lightgray;
  display: flex;
  justify-content: center;
  align-items: center;
  box-shadow: 0 0 10px rgba(0,0,0,0.5);

}
.link {
  margin-left: 20px;
  text-decoration: none;
  color: white;
  font-size: 24px;
}
.link:first-child {
  margin-left: 0px;
}

</style>