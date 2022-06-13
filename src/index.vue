<template>

  <div id="app">
    <app-header/>
    <main-index/>
  </div>

</template>

<script>

import appHeader from '@/components/appHeader/appHeader.vue'
import mainIndex from '/pages/mainIndex.vue'

export default {
  name: 'App',
  components: {
    appHeader,
    mainIndex
  }
}
</script>


<style>
@import "../assets/scss/common.css";
</style>
