<template>
  <header>
    <div class="header-content" >
      <div class="header" :class="{none_color: scrollPosition < 50, change_color: scrollPosition > 50}">
        <div class="header__wrap" :class="{hover_color:currentTab}">
          <div class="logo">
            <a href="#">
              <span class="blind">성원애드피아 로고</span>
            </a>
          </div>
          <!-- hover area -->
          <div class="nav" >
            <ul>
              <li v-for="(tab, index) in tabList" :key="index" :class="{active:currentTab === index}">
                <a href="#" @mouseover.prevent="currentTab = index +1" >{{ tab }}</a>
                <span :class="{tabmenu_color:currentTab === index+1}"></span>
              </li>
            </ul>
          </div>
          <!-- search area -->
          <div class="nav__search">
            <ul>
              <li><img src="../../../assets/images/dummy/icon_header_search.svg" alt="검색"></li>
              <li><img src="../../../assets/images/common/icon_mypage_off.svg" alt="검색"></li>
              <li><img src="../../../assets/images/common/icon_basket_off.svg" alt="검색"></li>
              <li @click="toggleMenu"><img src="../../../assets/images/dummy/icon_header_navi.svg" alt="전체메뉴"></li>
            </ul>
          </div>
        </div>
        <!-- quick area -->
        <div class="quick-content">
          <div class="quickNav" @click="quickShow = !quickShow"><span class="quick-title">QUICK <em>SERVICE</em></span>
              <span class="quickBtn" :class="{rotate:quickShow}"><img src="../../../assets/images/common/quick-arrow.svg" alt="검색"></span>
            </div>
          <!--menu-->
          <transition name="slide">
            <div class="quickList" v-if="quickShow" >
              <div class="quick-main">
                <ul>
                  <li v-for="(quickMain, index) in mainMenu" :key="index" class="info-menu" :class="{active:quickTab === index}">
                    <a href="#"  @mouseover.prevent="quickTab = index +1">
                    <figure>
                      <img :src="quickMain.product1.img" :alt="quickMain.product1.alt">
                    </figure>
                    </a>
                  </li>
                </ul>
              </div>
              <div class="quick-sub" >
                <ul>
                  <li v-show="quickTab == 1" class="sub-menu submenu01" @mouseleave.prevent="quickTab = 0">
                    <div class="sub-wrap submenu01--list">
                      <ul>
                        <li class="sub-list"><span class="sub-content sub-content--01"><p>1:1상담</p></span></li>
                        <li class="sub-list"><span class="sub-content sub-content--02"><p>성원톡</p></span></li>
                        <li class="sub-list"><span class="sub-content sub-content--03"><p>A/S상담</p></span></li>
                        <li class="sub-on"><p>실시간&nbsp;상담</p></li>
                      </ul>
                    </div>
                  </li>
                  <li v-show="quickTab == 2" class="sub-menu submenu02" @mouseleave.prevent="quickTab = 0">
                    <div class="sub-wrap submenu02--list">
                      <ul>
                        <li class="sub-list"><span class="sub-content sub-content--01"><p>상품가이드</p></span></li>
                        <li class="sub-list"><span class="sub-content sub-content--02"><p>주문가이드</p></span></li>
                        <li class="sub-list"><span class="sub-content sub-content--03"><p>인쇄가이드</p></span></li>
                        <li class="sub-on"><p>가이드</p></li>
                      </ul>
                    </div>
                  </li>
                  <li v-show="quickTab == 3" class="sub-menu submenu03" @mouseleave.prevent="quickTab = 0">
                    <div class="sub-wrap submenu03--list">
                      <ul>
                        <li class="sub-on only"><p>상품소개</p></li>
                      </ul>
                    </div>
                  </li>
                  <li v-show="quickTab == 4" class="sub-menu submenu04" @mouseleave.prevent="quickTab = 0">
                    <div class="sub-wrap submenu04--list">
                      <ul>
                        <li class="sub-on only"><p>고객센터</p></li>
                      </ul>
                    </div>
                  </li>
                  <li v-show="quickTab == 5" class="sub-menu submenu05" @mouseleave.prevent="quickTab = 0">
                    <div class="sub-wrap submenu05--list">
                      <ul>
                        <li class="sub-on only"><p>서체자료실</p></li>
                      </ul>
                    </div>
                  </li>
                  <li v-show="quickTab == 6" class="sub-menu submenu06" @mouseleave.prevent="quickTab = 0">
                    <div class="sub-wrap submenu06--list">
                      <ul>
                        <li class="sub-on only"><p>최근주문상품</p></li>
                      </ul>
                    </div>
                  </li>
                  <li v-show="quickTab == 7" class="sub-menu submenu07" @mouseleave.prevent="quickTab = 0">
                    <div class="sub-wrap submenu07--list">
                      <ul>
                        <li class="sub-on only"><p>장바구니</p></li>
                      </ul>
                    </div>
                  </li>
                  <li v-show="quickTab == 8" class="sub-menu submenu08" @mouseleave.prevent="quickTab = 0">
                    <div class="sub-wrap submenu08--list">
                      <ul>
                        <li class="sub-on only"><p>나만의&nbsp;견적</p></li>
                      </ul>
                    </div>
                  </li>
                  <li v-show="quickTab == 9" class="sub-menu submenu09" @mouseleave.prevent="quickTab = 0">
                    <div class="sub-wrap submenu09--list">
                      <ul>
                        <li class="sub-on only"><p>등급별혜택</p></li>
                      </ul>
                    </div>
                  </li>
                </ul>
              </div>
            </div>
          </transition>
        </div>
      </div>

      <!-- hover tab -->
      <div class="nav-bg" v-if="currentTab">
        <div v-show="currentTab == 1" class="nav__hoverTab" @mouseleave.prevent="currentTab = 0">
          <div class="nav__hoverTab--title">
            <div class="title-wrap">
              <figure>
                <img src="../../../assets/images/common/icon_hovermenu_card.svg" alt="명함 인쇄">
              </figure>
              <h3>명함 인쇄</h3>
              <p>나만의 아이덴티티로<br> 자신을 알려보세요.</p>
            </div>
          </div>
          <div class="nav__hoverTab--product">
            <ul>
              <li>
                <div class="accordions" v-for="(row, index) in navList01" :key="index">
                  <dl v-if="row.only == true">
                    <dt class="subtitle">
                      <figure>
                        <img :src="row.img" :alt="row.alt">
                      </figure>
                      <strong v-html="row.term"/>
                    </dt>
                  </dl>
                  <dl v-else>
                    <dt class="subtitle" :class="{border:row.open01}" @click="row.open01 = !row.open01">
                      <figure>
                        <img :src="row.img" :alt="row.alt">
                      </figure>
                      <strong>{{ row.term }}</strong> <span class="drop-down" :class="{rotate:row.open01}"><img src="../../../assets/images/common/icon_dropdown_blue.svg" alt="검색"></span></dt>
                    <template v-if="row.open01">
                      <dd class="bullet" v-for="(item,index) in row.items" :key="index"><span>{{ item.text }}</span><em class="tabmenu_color"></em></dd>
                    </template>
                  </dl>
                </div>
              </li>
            </ul>
          </div>
        </div>
        <div v-show="currentTab == 2" class="nav__hoverTab" @mouseleave.prevent="currentTab = 0">
          <div class="nav__hoverTab--title">
            <div class="title-wrap">
              <figure>
                <img src="../../../assets/images/common/icon_hovermenu_ad.svg" alt="명함 인쇄">
              </figure>
              <h3>광고·홍보</h3>
              <p>나만의 아이덴티티로<br> 자신을 알려보세요.</p>
            </div>
          </div>
          <div class="nav__hoverTab--product">
            <ul>
              <li>
                <div class="accordions" v-for="(row, index) in navList02" :key="index">
                  <dl v-if="row.only == true">
                    <dt class="subtitle">
                      <figure>
                        <img :src="row.img" :alt="row.alt">
                      </figure>
                      <strong v-html="row.term"/>
                    </dt>
                  </dl>
                  <dl v-else>
                    <dt class="subtitle" :class="{border:row.open02}" @click="row.open02 = !row.open02">
                      <figure>
                        <img :src="row.img" :alt="row.alt">
                      </figure>
                      <strong>{{ row.term }}</strong> <span class="drop-down" :class="{rotate:row.open02}"><img src="../../../assets/images/common/icon_dropdown_blue.svg" alt="검색"></span></dt>
                    <template v-if="row.open02">
                      <dd class="bullet" v-for="(item,index) in row.items" :key="index"><span>{{ item.text }}</span><em class="tabmenu_color"></em></dd>
                    </template>
                  </dl>
                </div>
              </li>
            </ul>
          </div>
        </div>
        <div v-show="currentTab == 3" class="nav__hoverTab" @mouseleave.prevent="currentTab = 0">
          <div class="nav__hoverTab--title">
            <div>
              <figure>
                <img src="../../../assets/images/common/icon_hovermenu_sticker.svg" alt="명함 인쇄">
              </figure>
              <h3>스티커</h3>
              <p>메세지를 간편하게<br>
                스티커로 전달하세요!</p>
            </div>
          </div>
          <div class="nav__hoverTab--product">
            <ul>
              <li>
                <div class="accordions" v-for="(row, index) in navList03" :key="index">
                  <dl v-if="row.only == true">
                    <dt class="subtitle">
                      <figure>
                        <img :src="row.img" :alt="row.alt">
                      </figure>
                      <strong v-html="row.term"/>
                    </dt>
                  </dl>
                  <dl v-else>
                    <dt class="subtitle" :class="{border:row.open03}" @click="row.open02 = !row.open03">
                      <figure>
                        <img :src="row.img" :alt="row.alt">
                      </figure>
                      <strong>{{ row.term }}</strong> <span class="drop-down" :class="{rotate:row.open03}"><img src="../../../assets/images/common/icon_dropdown_blue.svg" alt="검색"></span></dt>
                    <template v-if="row.open03">
                      <dd class="bullet" v-for="(item,index) in row.items" :key="index"><span>{{ item.text }}</span><em class="tabmenu_color"></em></dd>
                    </template>
                  </dl>
                </div>
              </li>
            </ul>
          </div>
        </div>
        <div v-show="currentTab == 4" class="nav__hoverTab" @mouseleave.prevent="currentTab = 0">
          <div class="nav__hoverTab--title">
            <div>
              <figure>
                <img src="../../../assets/images/common/icon_hovermenu_letter.svg" alt="봉투">
              </figure>
              <h3>봉투</h3>
              <p>다양한 제질과 사이즈제작<br>
                정서스러운 정보전달!</p>
            </div>
          </div>
          <div class="nav__hoverTab--product">
            <ul>
              <li>
                <div class="accordions" v-for="(row, index) in navList04" :key="index">
                  <dl v-if="row.only == true">
                    <dt class="subtitle">
                      <figure>
                        <img :src="row.img" :alt="row.alt">
                      </figure>
                      <strong v-html="row.term"/>
                    </dt>
                  </dl>
                  <dl v-else>
                    <dt class="subtitle" :class="{border:row.open04}" @click="row.open04 = !row.open04">
                      <figure>
                        <img :src="row.img" :alt="row.alt">
                      </figure>
                      <strong>{{ row.term }}</strong> <span class="drop-down" :class="{rotate:row.open04}"><img src="../../../assets/images/common/icon_dropdown_blue.svg" alt="검색"></span></dt>
                    <template v-if="row.open04">
                      <dd class="bullet" v-for="(item,index) in row.items" :key="index"><span>{{ item.text }}</span><em class="tabmenu_color"></em></dd>
                    </template>
                  </dl>
                </div>
              </li>
            </ul>
          </div>
        </div>
        <div v-show="currentTab == 5" class="nav__hoverTab" @mouseleave.prevent="currentTab = 0">
          <div class="nav__hoverTab--title">
            <figure>
              <img src="../../../assets/images/common/icon_hovermenu_book.svg" alt="명함 인쇄">
            </figure>
            <h3>책·카탈로그</h3>
            <p>나만의 아이덴티티로<br> 자신을 알려보세요.</p>
          </div>
          <div class="nav__hoverTab--product">
            <ul>
              <li>
                <div class="accordions" v-for="(row, index) in navList05" :key="index">
                  <dl v-if="row.only == true">
                    <dt class="subtitle">
                      <figure>
                        <img :src="row.img" :alt="row.alt">
                      </figure>
                      <strong v-html="row.term"/>
                    </dt>
                  </dl>
                  <dl v-else>
                    <dt class="subtitle" :class="{border:row.open05}" @click="row.open05 = !row.open05">
                      <figure>
                        <img :src="row.img" :alt="row.alt">
                      </figure>
                      <strong>{{ row.term }}</strong> <span class="drop-down" :class="{rotate:row.open05}"><img src="../../../assets/images/common/icon_dropdown_blue.svg" alt="검색"></span></dt>
                    <template v-if="row.open05">
                      <dd class="bullet" v-for="(item,index) in row.items" :key="index"><span>{{ item.text }}</span><em class="tabmenu_color"></em></dd>
                    </template>
                  </dl>
                </div>
              </li>
            </ul>
          </div>
        </div>
        <div v-show="currentTab == 6" class="nav__hoverTab" @mouseleave.prevent="currentTab = 0">
          <div class="nav__hoverTab--title">
            <div>
            <figure>
              <img src="../../../assets/images/common/icon_hovermenu_package.svg" alt="패키지">
            </figure>
            <h3>패키지</h3>
            <p>개성있는 브랜드를 한곳에!<br>
              고품격 인쇄로 제품의 질UP</p>
            </div>
          </div>
          <div class="nav__hoverTab--product">
            <ul>
              <li>
                <div class="accordions" v-for="(row, index) in navList06" :key="index">
                  <dl v-if="row.only == true">
                    <dt class="subtitle">
                      <figure>
                        <img :src="row.img" :alt="row.alt">
                      </figure>
                      <strong v-html="row.term"/>
                    </dt>
                  </dl>
                  <dl v-else>
                    <dt class="subtitle" :class="{border:row.open06}" @click="row.open06 = !row.open06">
                      <figure>
                        <img :src="row.img" :alt="row.alt">
                      </figure>
                      <strong>{{ row.term }}</strong> <span class="drop-down" :class="{rotate:row.open06}"><img src="../../../assets/images/common/icon_dropdown_blue.svg" alt="검색"></span></dt>
                    <template v-if="row.open06">
                      <dd class="bullet" v-for="(item,index) in row.items" :key="index"><span>{{ item.text }}</span><em class="tabmenu_color"></em></dd>
                    </template>
                  </dl>
                </div>
              </li>
            </ul>
          </div>
        </div>
        <div v-show="currentTab == 7" class="nav__hoverTab" @mouseleave.prevent="currentTab = 0">
          <div class="nav__hoverTab--title">
            <div class="title-wrap">
              <figure >
                <img src="../../../assets/images/common/icon_hovermenu_info.svg" alt="판촉물">
              </figure>
              <h3>판촉물</h3>
              <p>고객에게 브랜드 전달을 위한<br>
                현명한 가격과 품질선택!</p>
            </div>

          </div>
          <div class="nav__hoverTab--product">
            <ul>
              <li>
                <div class="accordions" v-for="(row, index) in navList07" :key="index">
                  <dl v-if="row.only == true">
                    <dt class="subtitle">
                      <figure>
                        <img :src="row.img" :alt="row.alt">
                      </figure>
                      <strong v-html="row.term"/>
                    </dt>
                  </dl>
                  <dl v-else>
                    <dt class="subtitle" :class="{border:row.open07}" @click="row.open07 = !row.open07">
                      <figure>
                        <img :src="row.img" :alt="row.alt">
                      </figure>
                      <strong>{{ row.term }}</strong> <span class="drop-down" :class="{rotate:row.open07}"><img src="../../../assets/images/common/icon_dropdown_blue.svg" alt="검색"></span></dt>
                    <template v-if="row.open07">
                      <dd class="bullet" v-for="(item,index) in row.items" :key="index"><span>{{ item.text }}</span><em class="tabmenu_color"></em></dd>
                    </template>
                  </dl>
                </div>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </div>


    <!-- Full Modal -->
    <div class="full-modal" v-if="openModal">
      <div class="modal-wrap">
        <h1>ALL MENU</h1>
        <div class="full-wrap">
          <div class="full-wrap__section">
            <h3 class="title">명함</h3>
            <div class="accordions" v-for="(row, index) in fullList01" :key="index">
              <dl v-if="row.only == true">
                <dt @click="row.open01 = !row.open">{{ row.term }}</dt>
              </dl>
            </div>
          </div>
          <div class="full-wrap__section">
            <h3 class="title">판촉물</h3>
            <div class="accordions" v-for="(row, index) in fullList02" :key="index">
              <dl v-if="row.only == true" >
                <dt @click="row.open02 = !row.open">{{ row.term }}</dt>
              </dl>
              <dl v-else >
                <dt @click="row.open02 = !row.open02" :class="{fullActive:row.open02}">{{ row.term }} <span :class="{rotate:row.open02}"><img src="../../../assets/images/common/icon_fullmenu_down.svg" alt="검색"></span></dt>
                <template v-if="row.open02">
                  <dd class="bullet" v-for="(item,index) in row.items" :key="index">{{ item.text }}</dd>
                </template>
              </dl>
            </div>
          </div>
          <div class="full-wrap__section">
            <h3 class="title">광고 · 홍보</h3>
            <div class="accordions" v-for="(row, index) in fullList03" :key="index">
              <dl v-if="row.only == true">
                <dt @click="row.open03 = !row.open">{{ row.term }}</dt>
              </dl>
              <dl v-else>
                <dt @click="row.open03 = !row.open03" :class="{fullActive:row.open03}">>{{ row.term }} <span :class="{rotate:row.open03}"><img src="../../../assets/images/common/icon_fullmenu_down.svg" alt="검색"></span></dt>
                <template v-if="row.open03">
                  <dd class="bullet" v-for="(item,index) in row.items" :key="index">{{ item.text }}</dd>
                </template>
              </dl>
            </div>
          </div>
          <div class="full-wrap__section">
            <h3 class="title">스티커</h3>
            <div class="accordions" v-for="(row, index) in fullList04" :key="index">
              <dl v-if="row.only == true">
                <dt @click="row.open04 = !row.open">{{ row.term }}</dt>
              </dl>
              <dl v-else>
                <dt @click="row.open04 = !row.open04" :class="{fullActive:row.open04}">>{{ row.term }} <span :class="{rotate:row.open04}"><img src="../../../assets/images/common/icon_fullmenu_down.svg" alt="검색"></span></dt>
                <template v-if="row.open04">
                  <dd class="bullet" v-for="(item,index) in row.items" :key="index">{{ item.text }}</dd>
                </template>
              </dl>
            </div>
          </div>
          <div class="full-wrap__section">
            <h3 class="title">봉투</h3>
            <div class="accordions" v-for="(row, index) in fullList05" :key="index">
              <dl v-if="row.only == true">
                <dt @click="row.open05 = !row.open">{{ row.term }}</dt>
              </dl>
              <dl v-else>
                <dt @click="row.open05 = !row.open05" :class="{fullActive:row.open05}">{{ row.term }} <span :class="{rotate:row.open05}"><img src="../../../assets/images/common/icon_fullmenu_down.svg" alt="검색"></span></dt>
                <template v-if="row.open05">
                  <dd class="bullet" v-for="(item,index) in row.items" :key="index">{{ item.text }}</dd>
                </template>
              </dl>
            </div>
          </div>
          <div class="full-wrap__section">
            <h3 class="title">책 · 카탈로그</h3>
            <div class="accordions" v-for="(row, index) in fullList06" :key="index">
              <dl v-if="row.only == true">
                <dt @click="row.open01 = !row.open">{{ row.term }}</dt>
              </dl>
              <dl v-else>
                <dt @click="row.open06 = !row.open06" :class="{fullActive:row.open06}">{{ row.term }} <span :class="{rotate:row.open06}"><img src="../../../assets/images/common/icon_fullmenu_down.svg" alt="검색"></span></dt>
                <template v-if="row.open06">
                  <dd class="bullet" v-for="(item,index) in row.items" :key="index">{{ item.text }}</dd>
                </template>
              </dl>
            </div>
          </div>
          <div class="full-wrap__section">
            <h3 class="title">패키지</h3>
            <div class="accordions" v-for="(row, index) in fullList07" :key="index">
              <dl v-if="row.only == true">
                <dt @click="row.open07 = !row.open">{{ row.term }}</dt>
              </dl>
              <dl v-else>
                <dt @click="row.open07 = !row.open07" :class="{fullActive:row.open07}">{{ row.term }} <span :class="{rotate:row.open07}"><img src="../../../assets/images/common/icon_fullmenu_down.svg" alt="검색"></span></dt>
                <template v-if="row.open07">
                  <dd class="bullet" v-for="(item,index) in row.items" :key="index">{{ item.text }}</dd>
                </template>
              </dl>
            </div>
          </div>
        </div>
        <span class="full-close" @click="openModal = false"><img src="../../../assets/images/dummy/icon_close.svg" alt="검색"></span>
      </div>
    </div>
    <!--test-->
  </header>

</template>

<script>


export default {
  components: {

  },

  methods: {
    scrollToTop() {
      window.scrollTo(0,0);
      console.log (window.scrollY)
    },
    toggleMenu () {
      this.openModal = !this.openModal
    },
    updateScroll(){
      this.scrollPosition = window.scrollY
      console.log (window.scrollY)
    },

  },
  mounted(){
    window.addEventListener('scroll', this.updateScroll);
  },
  props: {

  },
  data() {
    return {
      fullToggle: false,
      scrollPosition: null,
      quickShow:false,
      openModal: false,
      currentTab: 0,
      quickTab: 0,
      tabList: [
        '명함',
        '광고.홍보',
        '스티커',
        '봉투',
        '책.카탈로그',
        '패키지',
        '판촉물',
      ],
      mainMenu: [
        {
          product1: {
            img: require("../../../assets/images/common/icon_quick_time_off.svg"),
            alt: '실시간 상담',
          }
        },
        {
          product1: {
            img: require("../../../assets/images/common/icon_quick_guide_off.svg"),
            alt: '가이드',
          }
        },
        {
          product1: {
            img: require("../../../assets/images/common/icon_quick_product_off.svg"),
            alt: '상품소개',
          }
        },
        {
          product1: {
            img: require("../../../assets/images/common/icon_quick_cs_off.svg"),
            alt: '고객센터',
          }
        },
        {
          product1: {
            img: require("../../../assets/images/common/icon_quick_font_off.svg"),
            alt: '서체자료실',
          }
        },
        {
          product1: {
            img: require("../../../assets/images/common/icon_quick_recent_off.svg"),
            alt: '최근주문상품',
          }
        },
        {
          product1: {
            img: require("../../../assets/images/common/icon_quick_cart_off.svg"),
            alt: '장바구니',
          }
        },
        {
          product1: {
            img: require("../../../assets/images/common/icon_quick_order_off.svg"),
            alt: '나만의 견적',
          }
        },
        {
          product1: {
            img: require("../../../assets/images/common/icon_quick_benefit_off.svg"),
            alt: '등급별혜택',
          }
        },
      ],
      //nav data
      navList01: {
        item1: {
          img: require("../../../assets/images/common/thum_name_1.png"),
          alt: '일반 명함',
          term: '일반 명함',
          only: true,
        /*
        open01: false,
          items: [
            {
              text: '초저가 전단지',
            },
            {
              text: '초저가 접지 전단지',
            },
            {
              text: '랑데부 실속 접지 전단지',
            },
            {
              text: '문어발 전단지',
            },
          ]
          */
        },
        item2: {
          img: require("../../../assets/images/common/thum_name_2.png"),
          alt: '컷팅 명함',
          term: '컷팅 명함',
          only: true,
        },
        item3: {
          img: require("../../../assets/images/common/thum_name_3.png"),
          alt: '볼록코팅 명함',
          term: '볼록코팅 명함',
          only: true
        },
        item4: {
          img: require("../../../assets/images/common/thum_name_4.png"),
          alt: '컬러지 명함',
          term: '컬러지 명함',
          only: true
        },
        item5: {
          img: require("../../../assets/images/common/thum_name_5.png"),
          alt: '투명 명함',
          term: '투명 명함',
          only: true
        },
        item6: {
          img: require("../../../assets/images/common/thum_name_6.png"),
          alt: '플라스틱 명함',
          term: '플라스틱 명함',
          only: true
        },
        item7: {
          img: require("../../../assets/images/common/thum_name_7.png"),
          alt: '하이브리드 명함',
          term: '하이브리드 명함',
          only: true
        },
        item8: {
          img: require("../../../assets/images/common/thum_name_8.png"),
          alt: '카드 명함',
          term: '카드 명함',
          only: true
        },
      },
      navList02: {
        item1: {
          img: require("../../../assets/images/common/thum_ad_1.png"),
          alt: '초저가 전단지',
          term: '초저가 전단지',
          only: true
        },
        item2: {
          img: require("../../../assets/images/common/thum_ad_2.png"),
          alt: '초저가 전단지',
          term: '초저가<br>접지 전단지',
          only: true
        },
        item3: {
          img: require("../../../assets/images/common/thum_ad_3.png"),
          alt: '랑데부 실속 전단지',
          term: '랑데부 실속 전단지',
          only: true
        },
        item4: {
          img: require("../../../assets/images/common/thum_ad_4.png"),
          alt: '랑데부 실속 접지 전단지',
          term: '랑데부<br>실속 접지 전단지',
          only: true
        },
        item5: {
          img: require("../../../assets/images/common/thum_ad_5.png"),
          alt: '문고리 전단지',
          term: '문고리 전단지',
          only: true
        },
        item6: {
          img: require("../../../assets/images/common/thum_ad_6.png"),
          alt: '문어발 전단지',
          term: '문어발 전단지',
          only: true
        },
        item7: {
          img: require("../../../assets/images/common/thum_ad_7.png"),
          alt: '스탠다드지 리플렛',
          term: '스탠다드지 리플렛',
          only: true
        },
        item8: {
          img: require("../../../assets/images/common/thum_ad_8.png"),
          alt: '프리미엄지 리플렛',
          term: '프리미엄지 리플렛',
          only: true
        },
        item9: {
          img: require("../../../assets/images/common/thum_ad_9.png"),
          alt: '판지 리플렛',
          term: '판지 리플렛',
          only: true
        },
        item10: {
          img: require("../../../assets/images/common/thum_ad_10.png"),
          alt: '접비 리플렛',
          term: '접비 리플렛',
          only: true
        },
        item11: {
          img: require("../../../assets/images/common/thum_ad_11.png"),
          alt: '미니 접지 리플렛',
          term: '미니 접지 리플렛',
          only: true
        },
        item12: {
          img: require("../../../assets/images/common/thum_ad_12.png"),
          alt: '스탠다드지 인쇄',
          term: '스탠다드지 인쇄',
          only: true
        },
        item13: {
          img: require("../../../assets/images/common/thum_ad_13.png"),
          alt: '프리미엄지 인쇄',
          term: '프리미엄지 인쇄',
          only: true
        },
        item14: {
          img: require("../../../assets/images/common/thum_ad_14.png"),
          alt: '스탠다드 엽서',
          term: '스탠다드 엽서',
          only: true
        },
        item15: {
          img: require("../../../assets/images/common/thum_ad_15.png"),
          alt: '프리미엄 엽서',
          term: '프리미엄 엽서',
          only: true
        },
      },
      navList03: {
        item1: {
          img: require("../../../assets/images/common/thum_sticker_1.png"),
          alt: '사각 스티커',
          term: '사각 스티커',
          only: true
        },
        item2: {
          img: require("../../../assets/images/common/thum_sticker_2.png"),
          alt: '모양 스티커',
          term: '모양 스티커',
          only: true
        },
        item3: {
          img: require("../../../assets/images/common/thum_sticker_3.png"),
          alt: '다이컷팅 스티커',
          term: '다이컷팅 스티커',
          only: true
        },
        item4: {
          img: require("../../../assets/images/common/thum_sticker_4.png"),
          alt: '주차 스티커',
          term: '주차 스티커',
          only: true
        },
        item5: {
          img: require("../../../assets/images/common/thum_sticker_5.png"),
          alt: '라벨 스티커',
          term: '라벨 스티커',
          only: true
        },
        item6: {
          img: require("../../../assets/images/common/thum_sticker_6.png"),
          alt: '롤 스티커',
          term: '롤 스티커',
          only: true
        },
        item7: {
          img: require("../../../assets/images/common/thum_sticker_7.png"),
          alt: '떡 메모지',
          term: '떡 메모지',
          only: true
        },
      },
      navList04: {
        item1: {
          img: require("../../../assets/images/common/thum_letter_1.png"),
          alt: '스탠다드 봉투',
          term: '스탠다드 봉투',
          only: true
        },
        item2: {
          img: require("../../../assets/images/common/thum_letter_2.png"),
          alt: '세로 봉투',
          term: '세로 봉투',
          only: true
        },
        item3: {
          img: require("../../../assets/images/common/thum_letter_3.png"),
          alt: '가로 봉투',
          term: '가로 봉투',
          only: true
        },
        item4: {
          img: require("../../../assets/images/common/thum_letter_4.png"),
          alt: '초대장 봉투',
          term: '초대장 봉투',
          only: true
        },
        item5: {
          img: require("../../../assets/images/common/thum_letter_5.png"),
          alt: '기성 봉투',
          term: '기성 봉투',
          only: true
        },
        item6: {
          img: require("../../../assets/images/common/thum_letter_6.png"),
          alt: '캘린더 봉투',
          term: '캘린더 봉투',
          only: true
        },
        item7: {
          img: require("../../../assets/images/common/thum_letter_7.png"),
          alt: '창 봉투',
          term: '창 봉투',
          only: true
        },
      },
      navList05: {
        item1: {
          img: require("../../../assets/images/common/thum_book_1.png"),
          alt: '책자',
          term: '책자',
          only: true
        },
        item2: {
          img: require("../../../assets/images/common/thum_book_2.png"),
          alt: '카탈로그',
          term: '카탈로그',
          only: true,
        },
        item3: {
          img: require("../../../assets/images/common/thum_book_3.png"),
          alt: '작품집',
          term: '작품집',
          only: true
        },
        item4: {
          img: require("../../../assets/images/common/thum_book_4.png"),
          alt: '제안서',
          term: '제안서',
          only: true
        },
        item5: {
          img: require("../../../assets/images/common/thum_book_5.png"),
          alt: '잡지',
          term: '잡지',
          only: true
        },
        item6: {
          img: require("../../../assets/images/common/thum_book_6.png"),
          alt: '마스터 책자',
          term: '마스터 책자',
          only: true
        },
      },
      navList06: {
        item1: {
          img: require("../../../assets/images/common/thum_package_1.png"),
          alt: '종이 박스',
          term: '종이 박스',
          only: true
        },
        item2: {
          img: require("../../../assets/images/common/thum_package_2.png"),
          alt: '플라스틱 박스',
          term: '플라스틱 박스',
          only: true
        },
        item3: {
          img: require("../../../assets/images/common/thum_package_3.png"),
          alt: '쇼핑백',
          term: '쇼핑백',
          only: true
        },
        item4: {
          img: require("../../../assets/images/common/thum_package_4.png"),
          alt: '행텍',
          term: '행텍',
          only: true
        },
        item5: {
          img: require("../../../assets/images/common/thum_package_5.png"),
          alt: '포장지',
          term: '포장지',
          only: true
        },
        item6: {
          img: require("../../../assets/images/common/thum_package_6.png"),
          alt: '종이홀더',
          term: '종이홀더',
          only: true
        },
        item7: {
          img: require("../../../assets/images/common/thum_package_7.png"),
          alt: '메뉴판',
          term: '메뉴판',
          only: true
        },
      },
      navList07: {
        item1: {
          img: require("../../../assets/images/common/thum_info_2.png"),
          alt: 'L 홀더',
          term: 'L 홀더',
          only: true
        },
        item2: {
          img: require("../../../assets/images/common/thum_info_3.png"),
          alt: '투포켓 홀더',
          term: '투포켓 홀더',
          only: true
        },
        item3: {
          img: require("../../../assets/images/common/thum_info_4.png"),
          alt: '클리어 파일',
          term: '클리어 파일',
          only: true
        },
        item4: {
          img: require("../../../assets/images/common/thum_info_5.png"),
          alt: '서류화일',
          term: '서류화일',
          only: true
        },
        item5: {
          img: require("../../../assets/images/common/thum_info_6.png"),
          alt: '부채',
          term: '부채',
          only: true
        },
        item6: {
          img: require("../../../assets/images/common/thum_info_7.png"),
          alt: '책갈피',
          term: '책갈피',
          only: true
        },
        item7: {
          img: require("../../../assets/images/common/thum_info_8.png"),
          alt: '종이썬탭',
          term: '종이썬탭',
          only: true
        },
        item8: {
          img: require("../../../assets/images/common/thum_info_9.png"),
          alt: 'PP썬캡',
          term: 'PP썬캡',
          only: true
        },
        item9: {
          img: require("../../../assets/images/common/thum_info_10.png"),
          alt: '포스트잇',
          term: '포스트잇',
          only: true
        },
        item10: {
          img: require("../../../assets/images/common/thum_info_11.png"),
          alt: '복권',
          term: '복권',
          only: true
        },
        item11: {
          img: require("../../../assets/images/common/thum_info_12.png"),
          alt: '상품권',
          term: '상품권',
          only: true
        },
        item12: {
          img: require("../../../assets/images/common/thum_info_13.png"),
          alt: '이벤트 쿠폰',
          term: '이벤트 쿠폰',
          only: true
        },
        item13: {
          img: require("../../../assets/images/common/thum_info_1.png"),
          alt: '적립 쿠폰',
          term: '적립 쿠폰',
          only: true
        },

      },
      groups: [
        {
          img: require("../../../assets/images/dummy/icon_dummy.svg"),
          alt: '퀵 아이콘',
          nameGroup: [
            {
              name:'1',
              img: require("../../../assets/images/dummy/icon_dummy.svg"),
              alt: '서브메뉴 아이콘',
            },
            {
              name:'2',
              img: require("../../../assets/images/dummy/icon_dummy.svg"),
              alt: '서브메뉴 아이콘',
            },
            {
              name:'3',
              img: require("../../../assets/images/dummy/icon_dummy.svg"),
              alt: '서브메뉴 아이콘',
            },
          ]
        },
      ],
      fullList01: {
        item1: {
          term: '일반 명함',
          only: true
        },
        item2: {
          term: '컷팅 명함',
          only: true
        },
        item3: {
          term: '블록코팅 명함',
          only: true
        },
        item4: {
          term: '컬러지 명함',
          only: true
        },
        item5: {
          term: '투명 명함',
          only: true
        },
        item6: {
          term: '플라스틱 명함',
          only: true
        },
        item7: {
          term: '하이브리드 명함',
          only: true
        },
        item8: {
          term: '카드',
          only: true
        }
      },
      fullList02: {
        /*item1: {
          term: '일반명함',
          open02: false,
          items: [
            {
              text: '명함1',
            },
            {
              text: '명함2',
            },
            {
              text: '명함3',
            },
            {
              text: '명함4',
            },
          ]
        },*/
        item1: {
          term: '초저가 전단지',
          only: true
        },
        item2: {
          term: '초저가 접지 전단지',
          only: true
        },
        item3: {
          term: '랑데부 실속 전단지',
          only: true
        },
        item4: {
          term: '랑데부 실속 접시 전단지',
          only: true
        },
        item5: {
          term: '문고리 전단지',
          only: true
        },
        item6: {
          term: '문어발 전단지',
          only: true
        },
        item7: {
          term: '스탠다드지 리플렛',
          only: true
        },
        item8: {
          term: '프리미엄지 리플렛',
          only: true
        },
        item9: {
          term: '판지 리플렛',
          only: true
        },
        item10: {
          term: '접지 리플렛',
          only: true
        },
        item11: {
          term: '미니 접지 리플렛',
          only: true
        },
        item12: {
          term: '스탠다드지 인쇄',
          only: true
        },
        item13: {
          term: '프리미엄지 인쇄',
          only: true
        },
        item14: {
          term: '스탠다드지엽서',
          only: true
        },
        item15: {
          term: '프리미엄지 엽서',
          only: true
        },
        item16: {
          term: '포스터',
          only: true
        },
      },
      fullList03: {
        item1: {
          term: '사각 스티커',
          only: true
        },
        item2: {
          term: '모양 스티커',
          only: true
        },
        item3: {
          term: '다이컷팅 스티커',
          only: true
        },
        item4: {
          term: '주차 스티커',
          only: true
        },
        item5: {
          term: '라벨 스티커',
          only: true
        },
        item6: {
          term: '롤스티커',
          only: true
        },
        item7: {
          term: '떡메모지',
          only: true
        },
      },
      fullList04: {
        item1: {
          term: '스탠다드 봉투',
          only: true
        },
        item2: {
          term: '세로 봉투',
          only: true
        },
        item3: {
          term: '가로 봉투',
          only: true
        },
        item4: {
          term: '초대장 봉투',
          only: true
        },
        item5: {
          term: '기성 봉투',
          only: true
        },
        item6: {
          term: '캘랜더 봉투',
          only: true
        },
        item7: {
          term: '창봉투',
          only: true
        },
      },
      fullList05: {
        item1: {
          term: '책자',
          only: true
        },
        item2: {
          term: '카탈로그',
          only: true
        },
        item3: {
          term: '작품집',
          only: true
        },
        item4: {
          term: '제안서',
          only: true
        },
        item5: {
          term: '잡지',
          only: true
        },
        item6: {
          term: '마스터책자',
          only: true
        },
      },
      fullList06: {
        item1: {
          term: '종이박스',
          only: true
        },
        item2: {
          term: '플라스틱 박스',
          only: true
        },
        item3: {
          term: '쇼핑백',
          only: true
        },
        item4: {
          term: '행텍',
          only: true
        },
        item5: {
          term: '포장지',
          only: true
        },
        item6: {
          term: '종이홀더',
          only: true
        },
        item7: {
          term: '메뉴판',
          only: true
        },
      },
      fullList07: {
        item1: {
          term: 'L홀더',
          only: true
        },
        item2: {
          term: '투포켓홀더',
          only: true
        },
        item3: {
          term: '클리어파일',
          only: true
        },
        item4: {
          term: '서류화일',
          only: true
        },
        item5: {
          term: '부채',
          only: true
        },
        item6: {
          term: '책갈피',
          only: true
        },
        item7: {
          term: '종이썬캡',
          only: true
        },
        item8: {
          term: 'PP썬캡',
          only: true
        },
        item9: {
          term: '포스트잇',
          only: true
        },
        item10: {
          term: '복권',
          only: true
        },
        item11: {
          term: '상품권',
          only: true
        },
        item12: {
          term: '이벤트 쿠폰',
          only: true
        },
        item13: {
          term: '적립쿠폰',
          only: true
        },
      },
    }
  }
}
</script>
<style>

@import "/assets/scss/appHeader.css";
@import "/assets/scss/common.css";
</style>
<style scoped>
</style>
