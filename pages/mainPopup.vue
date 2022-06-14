<template>
  <div class="popup" v-if="openPopup">
    <div class="popup__content">
      <div class="popup__content-title">안내사항 알려드립니다.</div>
      <div class="popup__content-text">
        2022 성원애드피아  홈페이지 디자인 및 아이디어 공모전<br >
        22년 4월 14일(목) ~ 5월 1일(일)까지 많은 참여 바랍니다.
      </div>
      <div class="popup__content-close">
        <div class="close__check">
          <input type="checkbox" name="close_chk" id="close_chk" class="inp-close" />
          <label for="close_chk" class="close-text">오늘하루 닫기</label>
        </div>
        <div @click="openPopup = false" class="close__btn"><span class="blind">닫기</span></div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  components: {
  },

  methods: {
    toggleMenu () {
      this.openPopup = !this.openPopup
    }
  },
  data() {
    return {
      openPopup: true,
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
