<template>
  <div class="backgroundBar">
    <div class="progressBar" ref="progressBar">
    </div>
    <div ref="num" id="number"></div>
  </div>

</template>

<script lang="js">
  import Vue from 'vue'

  export default Vue.extend({
    props:['item'],
    data() {
      return {
        progress: 0
      }
    },
    mounted(){
      this.progressMath
      this.progressLine(this.item.progress, "#number")
    },
    methods: {
      progressLine(num, elem) {
        const time = 500;
        const step = 1;
          let n = this.progress;
          let t = Math.round(time / (num / step));
          let interval = setInterval(() => {
            n = n + step;
            if (this.$refs.num) {
              if (n == num) {
                clearInterval(interval);
              }
              this.$refs.num.innerHTML = `${n}%`;
            } else {
                clearInterval(interval);
            }
          }, t);
        }
    },
    computed:{
      progressMath(){
        if (this.item) {
          this.$refs.progressBar.style.width = `${this.item.progress}%`
          console.log(this.$refs.progressBar);
        }
      }
    }
  })
</script>

<style scoped>
.backgroundBar {
  margin-bottom: 50px;
  height: 10px;
  width: 241px;
  background: rgb(160, 149, 149);
  border-radius: 25px;
}
.progressBar {
  height: 10px;
  width: 0%;
  background: rgb(74, 101, 190);
  border-radius: 25px;
  transition: all 1s;
}
</style>