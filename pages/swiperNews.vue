<template>
  <swiper class="swiper3" :options="swiperOption">
    <swiper-slide>
      <a href="">
        <div class="title">공지사항</div>
        <div class="subject">
          [보도자료] 성원애드피아, 전국재해구호협회에 산불피해 이웃돕기 성금
        </div>
        <div class="date">2022-04-14</div>
      </a>
    </swiper-slide>
    <swiper-slide>
      <a href="">
        <div class="title">공지사항</div>
        <div class="subject">
          [보도자료] 성원애드피아, 전국재해구호협회에 산불피해 이웃돕기 성금
        </div>
        <div class="date">2022-04-14</div>
      </a>
    </swiper-slide>
    <swiper-slide>
      <a href="">
        <div class="title">공지사항</div>
        <div class="subject">
          [보도자료] 성원애드피아, 전국재해구호협회에 산불피해 이웃돕기 성금
        </div>
        <div class="date">2022-04-14</div>
      </a>
    </swiper-slide>
    <swiper-slide>
      <a href="">
        <div class="title">공지사항</div>
        <div class="subject">
          [보도자료] 성원애드피아, 전국재해구호협회에 산불피해 이웃돕기 성금
        </div>
        <div class="date">2022-04-14</div>
      </a>
    </swiper-slide>
    <swiper-slide>
      <a href="">
        <div class="title">공지사항</div>
        <div class="subject">
          [보도자료] 성원애드피아, 전국재해구호협회에 산불피해 이웃돕기 성금
        </div>
        <div class="date">2022-04-14</div>
      </a>
    </swiper-slide>
    <swiper-slide>
      <a href="">
        <div class="title">공지사항</div>
        <div class="subject">
          [보도자료] 성원애드피아, 전국재해구호협회에 산불피해 이웃돕기 성금
        </div>
        <div class="date">2022-04-14</div>
      </a>
    </swiper-slide>
    <swiper-slide>
      <a href="">
        <div class="title">공지사항</div>
        <div class="subject">
          [보도자료] 성원애드피아, 전국재해구호협회에 산불피해 이웃돕기 성금
        </div>
        <div class="date">2022-04-14</div>
      </a>
    </swiper-slide>
    <swiper-slide>
      <a href="">
        <div class="title">공지사항</div>
        <div class="subject">
          [보도자료] 성원애드피아, 전국재해구호협회에 산불피해 이웃돕기 성금
        </div>
        <div class="date">2022-04-14</div>
      </a>
    </swiper-slide>
    <div class="swiper-button-prev" slot="button-prev"></div>
    <div class="swiper-button-next" slot="button-next"></div>
  </swiper>
</template>

<script>
import { Swiper, SwiperSlide } from 'vue-awesome-swiper'
import 'swiper/css/swiper.css'
export default {
  name: 'swiper-news',
  components: {
    Swiper,
    SwiperSlide
  },
  data() {
    return {
      swiperOption: {
        slidesPerView: 'auto',
        spaceBetween: 40,
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        },
        autoplay: {
          delay: 5000,
          disableOnInteraction: false
        },
        loop: true
      }
    }
  }
}
</script>
<style>
@import "../assets/scss/swiper.css";
</style>
<style scoped>

</style>
