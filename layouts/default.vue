<template lang='html'>
    <div>
        <Header/>
        <Nuxt />
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Header from '~/components/pages/common/HeaderSidebar/index.vue'
export default Vue.extend({
    components: {
        Header,
    }
  
})
</script>

<style lang="scss" scoped>

</style>