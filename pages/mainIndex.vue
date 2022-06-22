<template>
  <div class="main">
    <full-page :options="options" id="fullpage" ref="fullpage">
      <div class="section" id="section0">
        <mainVisual />
      </div>
      <div class="section" id="section1">
        <div class="section__title">
          <div class="title-eng">NEW PRODUCT</div>
          <div class="title-kor">새롭게 준비됐어요!</div>
          <a href="#" class="btn-more">더보기</a>
        </div>
        <!-- s: new product -->
        <div class="new-product__swiper">
          <swiperProduct />
        </div>
        <!-- e: new product -->
      </div>
      <div class="section" id="section2">
        <div class="section__inner">
          <div class="section__title">
            <div class="title-eng">BEST PRODUCT</div>
            <div class="title-kor">
              <p>주목!</p>
              <p>인기상품</p>
            </div>
            <a href="#" class="btn-more">더보기</a>
          </div>
          <!-- s: best product -->
          <div class="best-product__list">
            <ul>
              <li>
                <a href="">
                  <div class="best-product__img">
                    <div class="img"><img src="../assets/images/main/best_product_01.jpg" alt="" /></div>
                    <div class="more">자세히보기</div>
                  </div>
                  <div class="best-product__content">
                    <div class="title">고급 명함지</div>
                    <div class="text">다양한 수입지로 고급스러운 나만의 명함</div>
                    <div class="detail">
                      <div class="info">
                        <span>90x50</span>
                        <span>200매</span>
                      </div>
                      <div class="price">16,050원</div>
                    </div>
                  </div>
                </a>
              </li>
              <li>
                <a href="">
                  <div class="best-product__img">
                    <div class="img"><img src="../assets/images/main/best_product_02.jpg" alt="" /></div>
                    <div class="more">자세히보기</div>
                  </div>
                  <div class="best-product__content">
                    <div class="title">일반 명함지</div>
                    <div class="text">가장 기본적이며 실용성의 명함</div>
                    <div class="detail">
                      <div class="info">
                        <span>90x50</span>
                        <span>500매</span>
                      </div>
                      <div class="price">4,620원</div>
                    </div>
                  </div>
                </a>
              </li>
              <li>
                <a href="">
                  <div class="best-product__img">
                    <div class="img"><img src="../assets/images/main/best_product_03.jpg" alt="" /></div>
                    <div class="more">자세히보기</div>
                  </div>
                  <div class="best-product__content">
                    <div class="title">디지털 엽서·상품권</div>
                    <div class="text">엽서 사이즈의 디지털 소량 인쇄</div>
                    <div class="detail">
                      <div class="info">
                        <span>100x148</span>
                        <span>8매</span>
                      </div>
                      <div class="price">2,310원</div>
                    </div>
                  </div>
                </a>
              </li>
              <li>
                <a href="">
                  <div class="best-product__img">
                    <div class="img"><img src="../assets/images/main/best_product_04.jpg" alt="" /></div>
                    <div class="more">자세히보기</div>
                  </div>
                  <div class="best-product__content">
                    <div class="title">도무송형 스티커</div>
                    <div class="text">우수한 접착력 및 경제적 규격</div>
                    <div class="detail">
                      <div class="info">
                        <span>40x60</span>
                        <span>1000매</span>
                      </div>
                      <div class="price">5,940원</div>
                    </div>
                  </div>
                </a>
              </li>
              <li>
                <a href="">
                  <div class="best-product__img">
                    <div class="img"><img src="../assets/images/main/best_product_05.jpg" alt="" /></div>
                    <div class="more">자세히보기</div>
                  </div>
                  <div class="best-product__content">
                    <div class="title">디지털 명함지</div>
                    <div class="text">여러지종 및 후가공 개성있는 명함</div>
                    <div class="detail">
                      <div class="info">
                        <span>90x50</span>
                        <span>96매</span>
                      </div>
                      <div class="price">4,950원</div>
                    </div>
                  </div>
                </a>
              </li>
              <li>
                <a href="">
                  <div class="best-product__img">
                    <div class="img"><img src="../assets/images/main/best_product_06.jpg" alt="" /></div>
                    <div class="more">자세히보기</div>
                  </div>
                  <div class="best-product__content">
                    <div class="title">포스터</div>
                    <div class="text">다양한 규격의 디지털 소량인쇄</div>
                    <div class="detail">
                      <div class="info">
                        <span>210x297</span>
                        <span>2매</span>
                      </div>
                      <div class="price">2,310원</div>
                    </div>
                  </div>
                </a>
              </li>
              <li>
                <a href="">
                  <div class="best-product__img">
                    <div class="img"><img src="../assets/images/main/best_product_07.jpg" alt="" /></div>
                    <div class="more">자세히보기</div>
                  </div>
                  <div class="best-product__content">
                    <div class="title">대·중·소 봉투</div>
                    <div class="text">가장 많이 사용되는 일반적인 봉투</div>
                    <div class="detail">
                      <div class="info">
                        <span>330x245</span>
                        <span>500매</span>
                      </div>
                      <div class="price">63,800원</div>
                    </div>
                  </div>
                </a>
              </li>
            </ul>
          </div>
          <!-- e: best product -->
        </div>
        <!-- s: banner -->
        <div class="setion__banner">
          <div class="banner__inner">
            <a href="#">
              <div class="text">
                <p>이젠 결제도 SPEED !</p>
                <p>간편 자동결제로 한번에!</p>
              </div>
              <div class="img"><img src="../assets/images/main/banner_img.png" alt="" /></div>
              <div class="text2">
                <img src="../assets/images/main/pay_ico.png" alt="">
                <p>언제 어디서든 쉽고 간편하게 이용하자!</p>
              </div>
            </a>
          </div>
        </div>
        <!-- e: banner -->
      </div>
      <div class="section" id="section3">
        <div class="section__title">
          <div class="title-eng">RECOMMENDED PRODUCT</div>
          <div class="title-kor">당신께 추천드려요!</div>
          <a href="#" class="btn-more">더보기</a>
        </div>
        <div class="section__inner">
          <!-- s: recommended product -->
          <div class="recom-product__list">
            <ul>
              <li class="sm">
                <a href="">
                  <div class="recom-product__img">
                    <img src="../assets/images/main/md_choice_small_01.jpg" alt="" />
                  </div>
                  <div class="recom-product__rank">
                    <div class="rank-num">02</div>
                    <div class="rank-name">best</div>
                  </div>
                  <div class="recom-product__content">
                    <div class="title">홍보물 책자</div>
                    <div class="tag">#디지털 #홍보용 #토너 #인디고</div>
                    <div class="detail">
                      <div class="info">
                        <span>삼각사이즈230x165</span>
                        <span>1부</span>
                      </div>
                      <div class="price">6,930원</div>
                    </div>
                  </div>
                </a>
              </li>
              <li class="sm">
                <a href="">
                  <div class="recom-product__img">
                    <img src="../assets/images/main/md_choice_small_02.jpg" alt="" />
                  </div>
                  <div class="recom-product__rank">
                    <div class="rank-num">03</div>
                    <div class="rank-name">best</div>
                  </div>
                  <div class="recom-product__content">
                    <div class="title">안내형 봉투</div>
                    <div class="tag">#봉투 #안내장 #내지 #모조지</div>
                    <div class="detail">
                      <div class="info">
                        <span>삼각사이즈230x165</span>
                        <span>1부</span>
                      </div>
                      <div class="price">6,930원</div>
                    </div>
                  </div>
                </a>
              </li>
              <li class="big">
                <a href="">
                  <div class="recom-product__img">
                    <img src="../assets/images/main/md_choice_big.jpg" alt="" />
                  </div>
                  <div class="recom-product__content">
                    <div class="tag">#디지털 #카달로그 #브로셔 #인디고인쇄</div>
                    <div class="title">디지털 카달로그 / 브로셔</div>
                  </div>
                  <div class="recom-product__detail">
                    <div class="info">
                      <span>A4사이즈</span>
                      <span>2부</span>
                    </div>
                    <div class="price">137,290원</div>
                  </div>
                </a>
              </li>
              <li class="sm">
                <a href="">
                  <div class="recom-product__img">
                    <img src="../assets/images/main/md_choice_small_03.jpg" alt="" />
                  </div>
                  <div class="recom-product__rank">
                    <div class="rank-num">04</div>
                    <div class="rank-name">best</div>
                  </div>
                  <div class="recom-product__content">
                    <div class="title">디지털 캘린더</div>
                    <div class="tag">#디지털 #캘린더 #브로셔 #인디고인쇄</div>
                    <div class="detail">
                      <div class="info">
                        <span>삼각사이즈230x165</span>
                        <span>1부</span>
                      </div>
                      <div class="price">6,930원</div>
                    </div>
                  </div>
                </a>
              </li>
              <li class="sm">
                <a href="">
                  <div class="recom-product__img">
                    <img src="../assets/images/main/md_choice_small_04.jpg" alt="" />
                  </div>
                  <div class="recom-product__rank">
                    <div class="rank-num">05</div>
                    <div class="rank-name">best</div>
                  </div>
                  <div class="recom-product__content">
                    <div class="title">디지털 책자</div>
                    <div class="tag">#디지털 #홍보용 #토너인쇄 #책자</div>
                    <div class="detail">
                      <div class="info">
                        <span>삼각사이즈230x165</span>
                        <span>1부</span>
                      </div>
                      <div class="price">6,930원</div>
                    </div>
                  </div>
                </a>
              </li>
            </ul>
          </div>
          <!-- e: recommended product -->
        </div>
      </div>
      <div class="section" id="section4">
        <div class="company__content">
          <!-- s: bi -->
          <div class="content__bi">
            <div class="section__inner">
              <div class="bi-item"><img src="../assets/images/main/bi_swadpia.png" alt=""></div>
              <div class="bi-item"><img src="../assets/images/main/bi_adpiamall.png" alt=""></div>
              <div class="bi-item"><img src="../assets/images/main/bi_foodmall.png" alt=""></div>
              <div class="bi-item"><img src="../assets/images/main/bi_logis.png" alt=""></div>
              <div class="bi-item"><img src="../assets/images/main/bi_stayrak.png" alt=""></div>
            </div>
          </div>
          <!-- e: bi -->
          <!-- s: news -->
          <div class="content__news">
            <div class="section__inner">
              <div class="news__title">
                <div class="title">
                  <span>news</span>
                  <a href=""><div class="blind">더보기</div></a>
                </div>
                <div class="text">고객여러분께 가장 빠른<br />소식을 알려 드립니다.</div>
              </div>
              <div class="news__swiper">
                <swiperNews />
              </div>
            </div>
          </div>
          <!-- e: news -->
          <app-footer/>
        </div>
      </div>
    </full-page>
    <a data-menuanchor="home" href="#home" class="top-scroll-btn"><em class="blind">Top</em></a>
    <!-- <span class="top-scroll-btn" @click="scrollToTop()"><em class="blind">Top</em></span> -->
  </div>
</template>

<script>
import mainVisual from '/src/components/mainVisual.vue'
import swiperProduct from '/pages/swiperProduct.vue'
import swiperNews from '/pages/swiperNews.vue'
import appFooter from '/src/components/appFooter/appFooter.vue'
import FullPage from 'vue-fullpage.js'
import $ from 'jquery'

export default {
  name: 'mainIndex',
  components: {
    mainVisual,
    swiperProduct,
    swiperNews,
    appFooter,
    FullPage
  },
  data() {
    return {
      options: {
        menu: '#menu',
        anchors: ['home', 'newProduct', 'bestProduct','mdChoice', 'footerPage'],
        controlArrows: false,
        navigation:true,
        navigationPosition:'left',
        navigationTooltips: ['Home', 'New Product','Best Product','MD Choice',''],
        showActiveTooltip: true,
        afterLoad: function (anchorLink, index) {
          if (index) {
            $('header').show();
            $('header .header-content .header').removeClass("change_color");
            $('header .header-content .header').addClass('none_color');
          }
          if(index>=2){
            $('header .header-content .header').addClass("change_color");
            $('header .header-content .header').removeClass('none_color');
          }
        },
      },
    }
  },
  destroyed() {
    $.fn.fullpage.destroy('all');
  }
}

</script>
<style>
@import "../assets/scss/main.css";
</style>
<style scoped>

</style>
