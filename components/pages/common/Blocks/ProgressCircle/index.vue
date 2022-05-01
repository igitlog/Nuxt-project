<template>
  <div class="boxCircleProgress">
    <div class="percent"  ref="block">
      <svg v-if="this.smallRadius">
        <circle class="circle" cx="500" cy="500" r="50" ref="layoutCircle"></circle>
        <circle class="progressCircle" cx="500" cy="500" r="50" ref="progressCircle"></circle>
      </svg>
      <!-- <div class="number">
        <h3 v-text="`${this.percent}%`" ></h3>
      </div> -->
    </div>
  </div>
</template>

<script lang="js">
  import Vue from 'vue'

  export default Vue.extend({
    props: ['smallPercent', 'smallRadius'],
    mounted(){
      this.setProgress
    },
    computed: {
      setProgress(){
        this.$refs.block.style.width = `${this.smallRadius * 2 + 20}px`
        this.$refs.block.style.height = `${this.smallRadius * 2 + 20}px`

        const circleRadius = this.smallRadius
        const circumference = 2 * Math.PI * circleRadius
        this.$refs.progressCircle.style.strokeDasharray = `${circumference} ${circumference}`
        this.$refs.progressCircle.style.strokeDashoffset = circumference
        
        this.$refs.progressCircle.style.r = this.smallRadius
        this.$refs.layoutCircle.style.r = this.smallRadius
        this.$refs.progressCircle.style.cx = this.smallRadius + 10
        this.$refs.layoutCircle.style.cx = this.smallRadius + 10
        this.$refs.progressCircle.style.cy = this.smallRadius + 10
        this.$refs.layoutCircle.style.cy = this.smallRadius + 10


        const offset = circumference - this.smallPercent / 100 * circumference
        this.$refs.progressCircle.style.strokeDashoffset = offset
      }
    },
  })
  // stroke-dasharray && stroke-dashoffset должны быть равны (Диаметр * 3)
</script>

<style scoped>
  .boxCircleProgress {
    position: absolute;
    left: 65px;
    top: 65px;

  }
    .percent{
      position: relative;
      width: 150px;
      height: 150px;
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
    .number {
      width: 100%;
      height: 100%;
      display: flex;
      align-items: center;
      justify-content: center;
      position: absolute;
      top: 0;
      left: 0;
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
            stroke-dasharray: 210;
            stroke-dashoffset: 210;
            transition: stroke-dashoffset 1.5s;

            stroke: rgb(67, 67, 134);
          }
</style>