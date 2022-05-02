<template>
  <div>
    <div v-for="(item, index) in this.data" :key="index" >
      <ProgressLine :item="item"/>
    </div>
    <div class="positioon">
      <ProgressCircle :smallPercent="smallPercent" :smallRadius="smallRadius"/>
      <MediumProgressCircle :mediumPercent="mediumPercent" :mediumRadius="mediumRadius"/>
      <BigProgressCircle 
        :innerPercent="innerPercent"
        :smallPercent="smallPercent"
        :mediumPercent="mediumPercent"
        :bigPercent="bigPercent"
        :bigRadius="bigRadius"/>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import ProgressLine from '~/components/pages/common/Blocks/ProgressLine/index.vue'
import ProgressCircle from '~/components/pages/common/Blocks/ProgressCircle/index.vue'
import MediumProgressCircle from '~/components/pages/common/Blocks/MediumProgressCircle/index.vue'
import BigProgressCircle from '~/components/pages/common/Blocks/BigProgressCircle/index.vue'

export default Vue.extend({
  name: 'MainPage',
  components: {
    ProgressLine,
    ProgressCircle,
    MediumProgressCircle,
    BigProgressCircle,
  },
  data() {
    return {
      innerPercent: 86,
      smallPercent: 75,
      smallRadius: 35,
      mediumPercent: 85,
      mediumRadius: 70,
      bigPercent: 90,
      bigRadius: 100,
      data: [
        {name: "adin", progress: 23},
        {name: "dwa", progress: 35},
        {name: "tblru", progress: 41},
        {name: "pat", progress: 64},
        {name: "sest", progress: 100},
      ]
    }
  },
})
</script>
<style scoped>

.positioon {
  position: relative;
  display: flex;
  width: 300px;
}

</style>
