<template>

  <div id="app">
    <app-header/>
    <main-index/>
    <app-footer/>
  </div>

</template>

<script>

import appHeader from '@/components/appHeader/appHeader.vue'
import appFooter from '@/components/appFooter/appFooter.vue'
import mainIndex from '/pages/mainIndex.vue'

export default {
  name: 'App',
  components: {
    appHeader,
    appFooter,
    mainIndex
  }
}
</script>


<style>
@import "../assets/scss/common.css";
</style>
