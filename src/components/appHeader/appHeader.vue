<template>
  <header>
    <div class="header-content" >
      <div class="header" :class="{none_color: scrollPosition < 50, change_color: scrollPosition > 50}">
        <div class="header__wrap" :class="{hover_color:currentTab}">
          <div class="logo">
            <a>
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
          <div class="quickNav" @click="quickShow = !quickShow"><span class="quick-title">Quick Menu</span>
              <span :class="{rotate:quickShow}"><img src="../../../assets/images/common/icon_btn_top.svg" alt="검색"></span>
            </div>
          <!--menu-->
          <transition name="slide">
            <div class="quickList" v-if="quickShow" >
              <div class="quick-main">
                <ul>
                  <li v-for="(quickMain, index) in mainMenu" :key="index" :class="{active:quickTab === index}">
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
                        <li><span class="sub-content sub-content--01"><p>배송현황1</p></span></li>
                        <li><span class="sub-content sub-content--02"><p>배송현황2</p></span></li>
                        <li class="sub-on"><p>배송현황</p></li>
                      </ul>
                    </div>
                  </li>
                  <li v-show="quickTab == 2" class="sub-menu submenu02" @mouseleave.prevent="quickTab = 0">
                    <div class="sub-wrap submenu02--list">
                      <ul>
                        <li><span class="sub-content sub-content--01"><p>성원톡1</p></span></li>
                        <li><span class="sub-content sub-content--02"><p>성원톡2</p></span></li>
                        <li><span class="sub-content sub-content--02"><p>성원톡3</p></span></li>
                        <li class="sub-on"><p>성원톡</p></li>
                      </ul>
                    </div>
                  </li>
                  <li v-show="quickTab == 3" class="sub-menu submenu03" @mouseleave.prevent="quickTab = 0">
                    <div class="sub-wrap submenu02--list">
                      <ul>
                        <li class="sub-on"><p>1:1상담</p></li>
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
            <h3>명함 인쇄</h3>
            <p>나만의 아이덴티티로<br> 자신을 알려보세요.</p>
          </div>
          <div class="nav__hoverTab--product">
            <ul>
              <li v-for="(info, index) in typeInfo01" :key="index">
                <a href="#">
                  <div class="category_product">
                    <figure>
                      <img :src="info.product.img" :alt="info.product.alt">
                    </figure>
                    <h3>{{ info.product.title }}</h3>
                  </div>
                </a>
              </li>
            </ul>
          </div>
        </div>
        <div v-show="currentTab == 2" class="nav__hoverTab" @mouseleave.prevent="currentTab = 0">
          <div class="nav__hoverTab--title">
            <h3>광고.홍보</h3>
            <p>나만의 아이덴티티로<br> 자신을 알려보세요.</p>
          </div>
          <div class="nav__hoverTab--product">
            <ul>
              <li v-for="(info, index) in typeInfo02" :key="index">
                <a href="#">
                  <div class="category_product">
                    <figure>
                      <img :src="info.product.img" :alt="info.product.alt">
                    </figure>
                    <h3>{{ info.product.title }}</h3>
                  </div>
                </a>
              </li>
            </ul>
          </div>
        </div>
        <div v-show="currentTab == 3" class="nav__hoverTab" @mouseleave.prevent="currentTab = 0">
          <div class="nav__hoverTab--title">
            <h3>스티커</h3>
            <p>나만의 아이덴티티로<br> 자신을 알려보세요.</p>
          </div>
          <div class="nav__hoverTab--product">
            <ul>
              <li v-for="(info, index) in typeInfo03" :key="index">
                <a href="#">
                  <div class="category_product">
                    <figure>
                      <img :src="info.product.img" :alt="info.product.alt">
                    </figure>
                    <h3>{{ info.product.title }}</h3>
                  </div>
                </a>
              </li>
            </ul>
          </div>
        </div>
        <div v-show="currentTab == 4" class="nav__hoverTab" @mouseleave.prevent="currentTab = 0">
          <div class="nav__hoverTab--title">
            <h3>봉투</h3>
            <p>나만의 아이덴티티로<br> 자신을 알려보세요.</p>
          </div>
          <div class="nav__hoverTab--product">
            <ul>
              <li v-for="(info, index) in typeInfo04" :key="index">
                <a href="#">
                  <div class="category_product">
                    <figure>
                      <img :src="info.product.img" :alt="info.product.alt">
                    </figure>
                    <h3>{{ info.product.title }}</h3>
                  </div>
                </a>
              </li>
            </ul>
          </div>
        </div>
        <div v-show="currentTab == 5" class="nav__hoverTab" @mouseleave.prevent="currentTab = 0">
          <div class="nav__hoverTab--title">
            <h3>책.카탈로그</h3>
            <p>나만의 아이덴티티로<br> 자신을 알려보세요.</p>
          </div>
          <div class="nav__hoverTab--product">
            <ul>
              <li v-for="(info, index) in typeInfo05" :key="index">
                <a href="#">
                  <div class="category_product">
                    <figure>
                      <img :src="info.product.img" :alt="info.product.alt">
                    </figure>
                    <h3>{{ info.product.title }}</h3>
                  </div>
                </a>
              </li>
            </ul>
          </div>
        </div>
        <div v-show="currentTab == 6" class="nav__hoverTab" @mouseleave.prevent="currentTab = 0">
          <div class="nav__hoverTab--title">
            <h3>패키지</h3>
            <p>나만의 아이덴티티로<br> 자신을 알려보세요.</p>
          </div>
          <div class="nav__hoverTab--product">
            <ul>
              <li v-for="(info, index) in typeInfo06" :key="index">
                <a href="#">
                  <div class="category_product">
                    <figure>
                      <img :src="info.product.img" :alt="info.product.alt">
                    </figure>
                    <h3>{{ info.product.title }}</h3>
                  </div>
                </a>
              </li>
            </ul>
          </div>
        </div>
        <div v-show="currentTab == 7" class="nav__hoverTab" @mouseleave.prevent="currentTab = 0">
          <div class="nav__hoverTab--title">
            <h3>판촉물</h3>
            <p>나만의 아이덴티티로<br> 자신을 알려보세요.</p>
          </div>
          <div class="nav__hoverTab--product">
            <ul>
              <li v-for="(info, index) in typeInfo07" :key="index">
                <a href="#">
                  <div class="category_product">
                    <figure>
                      <img :src="info.product.img" :alt="info.product.alt">
                    </figure>
                    <h3>{{ info.product.title }}</h3>
                  </div>
                </a>
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
              <dl v-else>
                <dt @click="row.open01 = !row.open01">{{ row.term }} <span :class="{rotate:row.open01}"><img src="../../../assets/images/common/icon_fullmenu_down.svg" alt="검색"></span></dt>
                <template v-if="row.open01">
                  <dd class="bullet" v-for="(item,index) in row.items" :key="index">{{ item.text }}</dd>
                </template>
              </dl>
            </div>
          </div>
          <div class="full-wrap__section">
            <h3 class="title">판촉물</h3>
            <div class="accordions" v-for="(row, index) in fullList02" :key="index">
              <dl v-if="row.only == true">
                <dt @click="row.open02 = !row.open">{{ row.term }}</dt>
              </dl>
              <dl v-else>
                <dt @click="row.open02 = !row.open02">{{ row.term }} <span :class="{rotate:row.open02}"><img src="../../../assets/images/common/icon_fullmenu_down.svg" alt="검색"></span></dt>
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
                <dt @click="row.open03 = !row.open01">{{ row.term }} <span :class="{rotate:row.open03}"><img src="../../../assets/images/common/icon_fullmenu_down.svg" alt="검색"></span></dt>
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
                <dt @click="row.open04 = !row.open04">{{ row.term }} <span :class="{rotate:row.open04}"><img src="../../../assets/images/common/icon_fullmenu_down.svg" alt="검색"></span></dt>
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
                <dt @click="row.open05 = !row.open05">{{ row.term }} <span :class="{rotate:row.open05}"><img src="../../../assets/images/common/icon_fullmenu_down.svg" alt="검색"></span></dt>
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
                <dt @click="row.open06 = !row.open06">{{ row.term }} <span :class="{rotate:row.open06}"><img src="../../../assets/images/common/icon_fullmenu_down.svg" alt="검색"></span></dt>
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
                <dt @click="row.open07 = !row.open07">{{ row.term }} <span :class="{rotate:row.open07}"><img src="../../../assets/images/common/icon_fullmenu_down.svg" alt="검색"></span></dt>
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
    }
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
      quickSub: false,
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
            img: require("../../../assets/images/dummy/icon_dummy_off.svg"),
            alt: '퀵 아이콘',
          }
        },
        {
          product1: {
            img: require("../../../assets/images/dummy/icon_dummy_off.svg"),
            alt: '퀵 아이콘',
          }
        },
        {
          product1: {
            img: require("../../../assets/images/dummy/icon_dummy_off.svg"),
            alt: '퀵 아이콘',
          }
        }
      ],
      typeInfo01: [
        {
          product: {
            title: '일반명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '컷팅명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },
        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '하이브리드 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '하이브리드 하이브리드 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '일반명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '일반명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        }

      ],
      typeInfo02: [
        {
          product: {
            title: '일반명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '컷팅명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
      ],
      typeInfo03: [
        {
          product: {
            title: '일반명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '컷팅명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '일반명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '컷팅명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '일반명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '컷팅명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '일반명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '컷팅명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
      ],
      typeInfo04: [
        {
          product: {
            title: '일반명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '컷팅명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '하이브리드 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '하이브리드 하이브리드 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '일반명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '일반명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        }

      ],
      typeInfo05: [
        {
          product: {
            title: '일반명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '컷팅명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
      ],
      typeInfo06: [
        {
          product: {
            title: '일반명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '컷팅명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
      ],
      typeInfo07: [
        {
          product: {
            title: '일반명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '컷팅명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },
        {
          product: {
            title: '볼록코팅 명함',
            img: require("../../../assets/images/dummy/img_header_icon.png"),
            alt: '일반명함',
          },

        },

      ],
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
          term: '일반명함',
          open01: false,
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
        },
        item2: {
          term: '컷팅명함',
          open01: false,
          items: [
            {
              text: 'test1',
            },
            {
              text: 'test2',
            },
            {
              text: 'test2',
            },
            {
              text: 'test2',
            },
          ]
        },
        item3: {
          term: '블록코팅 명함',
          only: true
        },
        item4: {
          term: '하이브리드 명함',
          only: true
        },
        item5: {
          term: '투명명함',
          only: true
        },
        item6: {
          term: '플라스틱 명함',
          only: true
        },
        item7: {
          term: '카드명함',
          only: true
        },
        item8: {
          term: '컷팅명함',
          only: true
        }
      },
      fullList02: {
        item1: {
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
        },
        item2: {
          term: '컷팅명함',
          open02: false,
          items: [
            {
              text: 'test1',
            },
            {
              text: 'test2',
            },
            {
              text: 'test2',
            },
            {
              text: 'test2',
            },
          ]
        },
        item3: {
          term: '블록코팅 명함',
          only: true
        },
        item4: {
          term: '하이브리드 명함',
          only: true
        }
      },
      fullList03: {
        item1: {
          term: '블록코팅 명함',
          only: true
        },
        item2: {
          term: '블록코팅 명함',
          only: true
        },
        item3: {
          term: '블록코팅 명함',
          only: true
        },
        item4: {
          term: '하이브리드 명함',
          only: true
        }
      },
      fullList04: {
        item1: {
          term: '블록코팅 명함',
          only: true
        },
        item2: {
          term: '블록코팅 명함',
          only: true
        },
      },
      fullList05: {
        item1: {
          term: '일반명함',
          open05: false,
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
        },
        item2: {
          term: '컷팅명함',
          open05: false,
          items: [
            {
              text: 'test1',
            },
            {
              text: 'test2',
            },
            {
              text: 'test2',
            },
            {
              text: 'test2',
            },
          ]
        },
        item3: {
          term: '블록코팅 명함',
          only: true
        },
        item4: {
          term: '하이브리드 명함',
          only: true
        }
      },
      fullList06: {
        item1: {
          term: '일반명함',
          open06: false,
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
        },
        item2: {
          term: '컷팅명함',
          open06: false,
          items: [
            {
              text: 'test1',
            },
            {
              text: 'test2',
            },
            {
              text: 'test2',
            },
            {
              text: 'test2',
            },
          ]
        },
        item3: {
          term: '블록코팅 명함',
          only: true
        },
        item4: {
          term: '하이브리드 명함',
          only: true
        }
      },
      fullList07: {
        item1: {
          term: '일반명함',
          open07: false,
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
        },
        item2: {
          term: '컷팅명함',
          open07: false,
          items: [
            {
              text: 'test1',
            },
            {
              text: 'test2',
            },
            {
              text: 'test2',
            },
            {
              text: 'test2',
            },
          ]
        },
        item3: {
          term: '블록코팅 명함',
          only: true
        },
        item4: {
          term: '하이브리드 명함',
          only: true
        }
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
