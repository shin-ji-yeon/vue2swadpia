<template>
  <div class="visual">
    <!-- s: swiper img -->
    <swiper class="swiper swiper__visual-img" :options="swiperOptionImg" ref="swiperImg">
      <swiper-slide class="slide-1"><img src="../assets/images/main/main_bgimg01.jpg" alt=""></swiper-slide>
      <swiper-slide class="slide-2"><img src="../assets/images/main/main_bgimg01.jpg" alt=""></swiper-slide>
      <swiper-slide class="slide-3"><img src="../assets/images/main/main_bgimg01.jpg" alt=""></swiper-slide>
      <swiper-slide class="slide-4"><img src="../assets/images/main/main_bgimg01.jpg" alt=""></swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
    <!-- e: swiper img -->
    <div class="visual__line">
      <!-- s: swiper2 text -->
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
      <!-- e: swiper2 text -->
      <!-- s: login -->
      <div class="section__login">
        <form name="" id="" method="" action="">
            <div class="login__idpw">
                <div class="input__row">
                  <div class="inp-ico ico-id"><span class="blind">아이디</span></div>
                  <input type="text" name="" id="" maxlength="40" class="inp-text" title="아이디" placeholder="아이디" />
                </div>
                <div class="input__row">
                  <div class="inp-ico ico-pw"><span class="blind">비밀번호</span></div>
                  <input type="password" name="" id="" maxlength="30" class="inp-text" title="비밀번호" placeholder="비밀번호" />
                </div>
            </div>
            <div class="login__remember">
              <input type="checkbox" name="user_saveid" id="user_saveid" class="inp-save" value="off" />
              <label for="user_saveid" class="save-text">아이디 저장</label>
            </div>
            <div class="login__btn">
                <button type="submit">로그인</button>
            </div>
            <ul class="login__find">
              <li><a href="#">아이디 찾기</a></li>
              <li><a href="#">비밀번호 찾기</a></li>
              <li><a href="#">회원가입</a></li>
            </ul>
        </form>
      </div>
      <!-- e: login -->
    </div>
    <div class="visual__scroll">
      <div class="text">SCROLL</div>
      <div class="ico"></div>
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