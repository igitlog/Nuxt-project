<template>
  <div class="container">
    <h1>
      <nuxt-link to="/calculators/financeCalc">Финансовый калькулятор</nuxt-link>
    </h1>
    <h1>
      <nuxt-link to="/calculators/simpleCalc">Обычный калькулятор</nuxt-link>
    </h1>
    <h1>
      <nuxt-link to="/calculators/oneCalc">Count +1</nuxt-link>
    </h1>
  </div>
</template>

<script lang="ts">
  import Vue from 'vue'

  export default Vue.extend({
    components: {
      
    }
  })
</script>

<style scoped>
  .container {
    display: flex;
    align-items: center;
    flex-direction: column;
  }
</style>