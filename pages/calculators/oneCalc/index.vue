<template>
<div class="page">
  <div class="pageTitle">
    <div v-text="`Click  on BUTTON if you want add 1`"/>
    <button v-on:click="addCount" >Count +1</button>
    <div v-text="`COUNT: ${count}`"/>
  </div>
</div>
</template>

<script lang="ts">
  import Vue from 'vue'

  export default Vue.extend({
    data() {
      return {
        count: 0,
      }
    },
    components: {
    },
    methods: {
      addCount () {
        this.count = this.count + 1;
      }
    },
    
  })
</script>

<style scoped>
.page {
  padding: 20px;
}
.pageTitle {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.pageTitle :nth-child(n) {
  margin: 15px 0;
}
</style>