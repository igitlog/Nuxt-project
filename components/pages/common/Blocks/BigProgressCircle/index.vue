<template>
  <div class="boxCircleProgress">
    <div class="percent"  ref="block">
      <svg v-if="this.bigRadius">
        <circle class="circle" cx="500" cy="500" r="50" ref="layoutCircle"></circle>
        <circle class="progressCircle" cx="500" cy="500" r="50" ref="progressCircle"></circle>
      </svg>
    </div>
    <div class="innerProgress">
      <h3 ref="num"></h3>
    </div>
    <div class="smallProgress">
      <h3 ref="num2"></h3>
    </div>
    <div class="mediumProgress">
      <h3 ref="num3"></h3>
    </div>
    <div class="bigProgress">
      <h3 ref="num4"></h3>
    </div>
  </div>
</template>

<script lang="js">
  import Vue from 'vue'

  export default Vue.extend({
    props: ['innerPercent', 'smallPercent', 'mediumPercent', 'bigPercent', 'bigRadius'],
    data() {
      return {
        progress: 0
      }
    },
    mounted(){
      this.setProgress
      this.innerProgress(this.innerPercent)
      this.smallProgress(this.smallPercent)
      this.mediumProgress(this.mediumPercent)
      this.bigProgress(this.bigPercent)
    },
    methods: {
      innerProgress(num) {
        const time = 1000;
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
        },
      smallProgress(num) {
        const time = 1000;
        const step = 1;
        let n = this.progress;
        let t = Math.round(time / (num / step));
        let interval = setInterval(() => {
            n = n + step;
            if (this.$refs.num) {
              if (n == num) {
                clearInterval(interval);
              }
              this.$refs.num2.innerHTML = `${n}%`;
            } else {
                clearInterval(interval);
            }
        }, t);
      },
      mediumProgress(num) {
        const time = 1000;
        const step = 1;
        let n = this.progress;
        let t = Math.round(time / (num / step));
        let interval = setInterval(() => {
            n = n + step;
            if (this.$refs.num) {
              if (n == num) {
                clearInterval(interval);
              }
              this.$refs.num3.innerHTML = `${n}%`;
            } else {
                clearInterval(interval);
            }
        }, t);
      },
      bigProgress(num) {
        const time = 1000;
        const step = 1;
        let n = this.progress;
        let t = Math.round(time / (num / step));
        let interval = setInterval(() => {
            n = n + step;
            if (this.$refs.num) {
              if (n == num) {
                clearInterval(interval);
              }
              this.$refs.num4.innerHTML = `${n}%`;
            } else {
                clearInterval(interval);
            }
        }, t);
      }
    },
    computed: {
      setProgress(){
        this.$refs.block.style.width = `${this.bigRadius * 2 + 20}px`
        this.$refs.block.style.height = `${this.bigRadius * 2 + 20}px`

        const circleRadius = this.bigRadius
        const circumference = 2 * Math.PI * circleRadius
        this.$refs.progressCircle.style.strokeDasharray = `${circumference} ${circumference}`
        this.$refs.progressCircle.style.strokeDashoffset = circumference
        
        this.$refs.progressCircle.style.r = this.bigRadius
        this.$refs.layoutCircle.style.r = this.bigRadius
        this.$refs.progressCircle.style.cx = this.bigRadius + 10
        this.$refs.layoutCircle.style.cx = this.bigRadius + 10
        this.$refs.progressCircle.style.cy = this.bigRadius + 10
        this.$refs.layoutCircle.style.cy = this.bigRadius + 10


        const offset = circumference - this.bigPercent / 100 * circumference
        this.$refs.progressCircle.style.strokeDashoffset = offset
      }
    },
  })
  // stroke-dasharray && stroke-dashoffset должны быть равны (Диаметр * 3)
  //       width && height .percent должны быть равны размеру svg
</script>

<style scoped>
  .boxCircleProgress {
    position: absolute;
    left: 0;
  }
    .percent{
      position: relative;
      width: 220px;
      height: 220px;
      border-radius: 50%;
    }
    .circle {
      transform-origin: center;
      transform: rotate(-90deg);
    }
    .progressCircle {
      transform-origin: center;
      transform: rotate(-90deg);
    }
    .innerProgress {
      width: 100%;
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      position: absolute;
      top: 0;
      left: 0;
    }
    .smallProgress {
      width: 100%;
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      position: absolute;
      top: -50px;
      left: 180px;
    }
    .mediumProgress {
      width: 100%;
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      position: absolute;
      top: 0px;
      left: 180px;
    }
    .bigProgress {
      width: 100%;
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      position: absolute;
      top: 50px;
      left: 180px;
    }

      svg {
        width: 100%;
        height: 100%;
        position: relative;
        z-index: 2;
      }
        circle {
          width: 100%;
          height: 100%;
          fill: none;
          stroke: gray;
          stroke-width: 12;
          stroke-linecap: round;
          transform: translate(5px,5px);
        }
          circle:nth-child(2) {
            stroke-dasharray: 600;
            stroke-dashoffset: 600;
            transition: stroke-dashoffset 1.5s;


            stroke: rgb(97, 168, 56);
          }
</style>