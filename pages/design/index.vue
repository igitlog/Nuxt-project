<template>
  <div class="container">
    <h1>
      Сложные штуки по верстке
    </h1>
    <h2>
      <nuxt-link to="/design/progressBars">Progress Bars</nuxt-link>
    </h2> 
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