<template>
  <FinanceCalculator/>
</template>

<script lang="ts">
  import Vue from 'vue'
  import FinanceCalculator from '~/components/pages/FinanceCalculator/index.vue'

  export default Vue.extend({
    components: {
      FinanceCalculator,
    }
    
  })
</script>

<style scoped>

</style>