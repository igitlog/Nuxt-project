<template>
  <div>
    <IndexPage></IndexPage>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import IndexPage from '~/components/pages/IndexPage/index.vue'
export default Vue.extend({
  name: 'MainPage',
  components: {
    IndexPage,
  }
})
</script>
<style>
body {
  margin: 0;
  padding: 0;
}
</style>
