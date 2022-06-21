<template>
  <div class="visual">
    <!-- s: swiper img -->
    <swiper class="swiper swiper__visual-img" :options="swiperOptionImg" ref="swiperImg">
      <swiper-slide class="slide-1"><img src="../../assets/images/main/main_bgimg_01.jpg" alt=""></swiper-slide>
      <swiper-slide class="slide-2"><img src="../../assets/images/main/main_bgimg_02.jpg" alt=""></swiper-slide>
      <swiper-slide class="slide-3"><img src="../../assets/images/main/main_bgimg_03.jpg" alt=""></swiper-slide>
      <swiper-slide class="slide-4"><img src="../../assets/images/main/main_bgimg_04.jpg" alt=""></swiper-slide>
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
            <span>#부채 초소량 제작가능</span>
            <span class="ml20">#다용도PP</span>
            <span>#시원한 여름준비</span>
            <span class="ml20">#여름 판촉을 부탁해!</span>
          </div>
        </swiper-slide>
        <swiper-slide class="slide-2">
          <a href="" class="btn"><span class="blind">자세히보기</span></a>
          <div class="sub-title">내가 원하는데로!</div>
          <div class="title">모양 포스트잇 4종</div>
          <div class="text">
            <span>#판촉물</span>
            <span class="ml20">#모양선택 제작가능</span>
            <span>#나만의 포스트잇</span>
            <span class="ml20">#신제품출시</span>
          </div>
        </swiper-slide>
        <swiper-slide class="slide-3">
          <a href="" class="btn"><span class="blind">자세히보기</span></a>
          <div class="sub-title">직접 디자인한</div>
          <div class="title">내 마음을 담은 봉투</div>
          <div class="text">
            <span>#엽서 한장</span>
            <span class="ml20">#인쇄의 모든것</span>
            <span>#다양한 선택</span>
            <span class="ml20">#디지털인쇄</span>
          </div>
        </swiper-slide>
        <swiper-slide class="slide-4">
          <a href="" class="btn"><span class="blind">자세히보기</span></a>
          <div class="sub-title">국민인쇄! 인쇄 유토피아!</div>
          <div class="title">대표인쇄 명함성지</div>
          <div class="text">
            <span>#상업인쇄</span>
            <span class="ml20">#비즈니스 첫걸음</span>
            <span>#인쇄의 모든것</span>
            <span class="ml20">#대표인쇄 명함</span>
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
@import "../../assets/scss/swiper.css";
</style>
<style lang="scss" scoped>
</style>
