<template>
  <header>
    <div class="header">
      <div class="header__wrap">
        <div class="logo">
          <a>
            <span class="blind">성원애드피아 로고</span>
          </a>
        </div>
<!--        <div class="nav" v-on:mouseover="mouseover">
          <ul>
            <li><a href="#">명함</a></li>
            <li><a href="#">광고.홍보</a></li>
            <li><a href="#">스티커</a></li>
            <li><a href="#">봉투</a></li>
            <li><a href="#">책.카탈로그</a></li>
            <li><a href="#">패키지</a></li>
            <li><a href="#">판촉물</a></li>
          </ul>
        </div>
        <div class="nav__search">
          <ul>
            <li>1</li>
            <li>2</li>
            <li>3</li>
            <li @click="toggleMenu">4</li>
          </ul>
        </div>-->
      </div>
    </div>

    <!-- hover -->
<!--    <div class="navHover" v-if="mouseover">
      <div class="navHover__title">
        <strong>명함인쇄</strong>
        <p>자신을 알려보세요</p>
      </div>
      <ul>
        <li>일반명함</li>
        <li>일반명함</li>
        <li>일반명함</li>
      </ul>
    </div>-->
    <!--  <FullMenu/>-->
    <div class="modaltest" v-if="openModal == true">
      <h2>모달</h2>
      <div>modal test</div>
      <div @click="openModal = false">닫기</div>
    </div>
  </header>


</template>

<script>
//import FullMenu from '@/components/AppHeader/FullMenu.vue'

export default {
  components: {
    //FullMenu
  },
  methods: {
    toggleMenu () {
      this.openModal = !this.openModal
      console.log('test');
    },
    mouseover () {
      alert("hi");
    }
  },
  data() {
    return {
      openModal: false
    }
  }
}
</script>
<style>
@import "./style.css";
</style>
<style scoped>

</style>
