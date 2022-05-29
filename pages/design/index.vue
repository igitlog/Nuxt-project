<template>
  <div class="container">
    <h1>
      Здесь будут готовые компоненты, которые можно будет использовать в ваших проектах.
      <p>Что стоит ожидать:</p>
      <p>- Никаких библиотек, обычные компоненты, которые можно скопировать и вставить к себе в проект.</p>
      <p>- Компонент можно изменять на ваше усмотрение и согласно вашим запросам.</p>
      <p>- Настраиваемые параметры, для удобной стилизации.</p>
      <p>- Вы получаете готовые шаблоны компонентов и ускоряете свою работу. </p>
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