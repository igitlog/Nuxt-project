<template>
<div class="page">
  <div class="pageTitle">
    <div v-text="`Click  on BUTTON if you want add 1`"/>
    <div ref="buttonField" class="field">
      <button ref="oneCalcButton" v-on:click="addCount(Bugaga)">Count +1</button>
    </div>
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
      addCount (Bugaga: any) {
        this.count = this.count + 1;
        Bugaga()
      },
      Bugaga() {
        if (this.count === 10) {
          (this.$refs.buttonField as any).style.width = `100%`;
          (this.$refs.buttonField as any).style.height = `250px`;
        }
        
        if ((this.count > 10) && (this.count < 21)) {
          let randomNumber = Math.floor(Math.random() * 201) - 100;
          (this.$refs.buttonField as any).style.position = `relative`;
          (this.$refs.buttonField as any).style.top = `${randomNumber}px`;
        } else if ((this.count > 20) && (this.count < 31)) {
          let randomNumber = Math.floor(Math.random() * 201) - 100;
          (this.$refs.buttonField as any).style.left = `${randomNumber}px`;
        } else if((this.count > 30) && (this.count < 36)) {
          let randomNumber = Math.floor(Math.random() * 201) - 100;
          (this.$refs.buttonField as any).style.top = `${randomNumber}px`;
          (this.$refs.buttonField as any).style.left = `${randomNumber}px`;
        } else if((this.count > 35) && (this.count < 41)) {
          let randomNumberOne = Math.floor(Math.random() * 201) - 100;
          (this.$refs.buttonField as any).style.top = `${randomNumberOne}px`;
          let randomNumberTwo = Math.floor(Math.random() * 201) - 100;
          (this.$refs.buttonField as any).style.left = `${randomNumberTwo}px`;
        }
        
      }
    },
    
  })
</script>

<style scoped>
.page {
  padding: 20px;
}
.field {
  max-width: 300px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.pageTitle {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.pageTitle :nth-child(n) {
  margin: 10px 0;
}
</style>