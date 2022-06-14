<template class="test">

  <div id="app">
    <app-header/>
    <main-index/>
    <main-popup/>
  </div>

</template>

<script>

import appHeader from '@/components/appHeader/appHeader.vue'
import mainIndex from '/pages/mainIndex.vue'
import mainPopup from '/pages/mainPopup.vue'

export default {
  name: 'App',
  components: {
    appHeader,
    mainIndex,
    mainPopup
  }
}
</script>

<style>
@import "../assets/scss/common.css";
</style>
