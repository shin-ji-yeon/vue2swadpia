<template>
  <div class="visual__swiper">
    <!-- swiper1 -->
    <swiper class="swiper swiper__visual-img" :options="swiperOptionImg" ref="swiperImg">
      <swiper-slide class="slide-1"><img src="../assets/images/main/main_bgimg01.jpg" alt=""></swiper-slide>
      <swiper-slide class="slide-2"><img src="../assets/images/main/main_bgimg01.jpg" alt=""></swiper-slide>
      <swiper-slide class="slide-3"><img src="../assets/images/main/main_bgimg01.jpg" alt=""></swiper-slide>
      <swiper-slide class="slide-4"><img src="../assets/images/main/main_bgimg01.jpg" alt=""></swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
    <div class="visual__line">
      <!-- swiper2 Thumbs -->
      <swiper class="swiper swiper__visual-text" :options="swiperOptionText" ref="swiperText">
        <swiper-slide class="slide-1">
          <a href="" class="btn"><span class="blind">자세히보기</span></a>
          <div class="sub-title">Hello! Summer</div>
          <div class="title">여름맞이 시즌상품</div>
          <div class="text">
            #부채 초소량 제작가능 #다용도PP<br />
            #시원한 여름준비 #여름 판촉을 부탁해!
          </div>
        </swiper-slide>
        <swiper-slide class="slide-2">
          <a href="" class="btn"><span class="blind">자세히보기</span></a>
          <div class="sub-title">Hello! Summer</div>
          <div class="title">여름맞이 시즌상품</div>
          <div class="text">
            #부채 초소량 제작가능 #다용도PP<br />
            #시원한 여름준비 #여름 판촉을 부탁해!
          </div>
        </swiper-slide>
        <swiper-slide class="slide-3">
          <a href="" class="btn"><span class="blind">자세히보기</span></a>
          <div class="sub-title">Hello! Summer</div>
          <div class="title">여름맞이 시즌상품</div>
          <div class="text">
            #부채 초소량 제작가능 #다용도PP<br />
            #시원한 여름준비 #여름 판촉을 부탁해!
          </div>
        </swiper-slide>
        <swiper-slide class="slide-4">
          <a href="" class="btn"><span class="blind">자세히보기</span></a>
          <div class="sub-title">Hello! Summer</div>
          <div class="title">여름맞이 시즌상품</div>
          <div class="text">
            #부채 초소량 제작가능 #다용도PP<br />
            #시원한 여름준비 #여름 판촉을 부탁해!
          </div>
        </swiper-slide>
      </swiper>
    </div>
  </div>
</template>

<script>
  import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
  import 'swiper/css/swiper.css'
  export default {
    name: 'swiper-example-thumbs-gallery',
    components: {
      Swiper,
      SwiperSlide
    },
    data() {
      return {
        swiperOptionImg: {
          slidesPerView: '1',
          autoplay: {
            delay: 5000,
            disableOnInteraction: false,
          },
          pagination: {
            el: '.swiper-pagination',
            clickable: true
          }
        },
        swiperOptionText: {
          slidesPerView: '1',
          slideToClickedSlide: true
        }
      }
    },
    mounted() {
      this.$nextTick(() => {
        const swiperImg = this.$refs.swiperImg.$swiper
        const swiperText = this.$refs.swiperText.$swiper
        swiperImg.controller.control = swiperText
        swiperText.controller.control = swiperImg
      })
    }
  }
</script>
<style>
@import "../assets/scss/swiper.css";
</style>
<style lang="scss" scoped>
</style>