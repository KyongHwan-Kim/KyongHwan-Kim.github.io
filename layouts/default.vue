<template>
  <v-app dark>
    <v-navigation-drawer
      v-if="$route.name != 'index' && $route.name != 'profile'"
      hide-overlay
      fixed
      permanent
      style="
        height: 100vh;
        transform: translateX(0%);
        width: 300px;
        max-height: calc(100%);
      "
    >
      <header
        class="header1"
        style="
          height: 85px;
          text-align: center;
          padding-top: 20px;
          background-color: #263238;
        "
      >
        <div class="banner-white-logo">
          <NLink class="text" nuxt to="/"> {{ selectNav.title }}</NLink>
        </div>
      </header>
      <div class="nav-bar">
        <v-list dense v-for="item in selectNav.items" :key="item.value">
          <v-list-item-group>
            <v-list-item @click="changeOpenChild(item.value)">
              <v-icon
                style="padding-right: 5px"
                v-if="item.child.length > 0 && item.isOpenChild"
              >
                mdi-menu-down
              </v-icon>
              <v-icon
                style="padding-right: 5px"
                v-else-if="item.child.length > 0 && !item.isOpenChild"
              >
                mdi-menu-right
              </v-icon>
              <v-icon style="padding-right: 15px" v-else />
              <v-list-item-title class="nav-level-one">{{
                item.title
              }}</v-list-item-title>
            </v-list-item>
          </v-list-item-group>
          <v-list-item-group
            v-model="navRoute"
            v-if="item.child.length > 0 && item.isOpenChild"
          >
            <div v-for="child in item.child" :key="child.value">
              <v-list-item style="">
                <v-list-item-title class="nav-level-two">{{
                  child.title
                }}</v-list-item-title>
              </v-list-item>
            </div>
          </v-list-item-group>
        </v-list>
      </div>
    </v-navigation-drawer>
    <!--v-if="$route.name!=='login'"-->
    <Header v-if="$route.name == 'index'" />
    <HeaderMini v-else />
    <v-main>
      <nuxt />
    </v-main>
    <Footer />
    <div class="floating-container">
      <div class="floating-button">+</div>
      <div class="element-container">
        <a href="google.com">
          <span class="float-element tooltip-left">
            <i class="material-icons">phone</i>
          </span>
        </a>
        <span class="float-element">
          <i class="material-icons">email</i>
        </span>
        <span class="float-element">
          <i class="material-icons">chat</i>
        </span>
      </div>
    </div>
  </v-app>
</template>

<script>
export default {
  head() {
    return {
      title: "비버의 개발 일지 | 환영합니다",
      meta: [
        {
          hid: "description",
          name: "비버의 개발 일지",
          content: "안녕하세요 비버입니다. 아니지 저스틴입니다.",
        },
      ],
    };
  },
  components: {
    Header: () => import("@/layouts/sections/Header"),
    HeaderMini: () => import("@/layouts/sections/HeaderMini"),
    Footer: () => import("@/layouts/sections/Footer"),
  },
  data() {
    return {
      nav: [
        {
          title: "비버의 개발일지",
          value: "tech",
          items: [
            {
              title: "Computer Science",
              value: "computer-science",
              isOpenChild: true,
              child: [
                { title: "2023", value: "2023" },
                { title: "2022", value: "2022" },
              ],
            },
            {
              title: "Language",
              value: "computer-language",
              isOpenChild: true,
              child: [
                { title: "2023", value: "2023" },
                { title: "2022", value: "2022" },
              ],
            },
            {
              title: "Back-End",
              value: "back-end",
              isOpenChild: true,
              child: [
                { title: "2023", value: "2023" },
                { title: "2022", value: "2022" },
              ],
            },
            {
              title: "Front-End",
              value: "front-end",
              isOpenChild: true,
              child: [
                { title: "2023", value: "2023" },
                { title: "2022", value: "2022" },
              ],
            },
            {
              title: "Mobile",
              value: "mobile",
              isOpenChild: true,
              child: [
                { title: "2023", value: "2023" },
                { title: "2022", value: "2022" },
              ],
            },
            {
              title: "Big Data",
              value: "big-data",
              isOpenChild: true,
              child: [
                { title: "2023", value: "2023" },
                { title: "2022", value: "2022" },
              ],
            },
            {
              title: "Algorithm",
              value: "algorithm",
              isOpenChild: true,
              child: [
                { title: "2023", value: "2023" },
                { title: "2022", value: "2022" },
              ],
            },
          ],
        },
        {
          title: "비버의 대회일지",
          value: "contest",
          items: [],
        },
        {
          title: "비버의 프로젝트",
          value: "project",
          items: [],
        },
        {
          title: "비버의 활동일지",
          value: "activity",
          items: [],
        },
        {
          title: "비버의 일상일지",
          value: "life",
          items: [
            {
              title: "Daily",
              value: "daily",
              isOpenChild: true,
              child: [
                { title: "2023", value: "2023" },
                { title: "2022", value: "2022" },
              ],
            },
            {
              title: "Think About",
              value: "think",
              isOpenChild: true,
              child: [],
            },
          ],
        },
      ],
      navRoute: {},
      selectNav: {
        title: "",
        value: "",
        items: [],
      },
    };
  },
  mounted() {
    this.selectNav = this.nav.find((item) => item.value == this.$route.name);
  },
  methods: {
    changeOpenChild(itemValue) {
      this.selectNav.items.find((item) => item.value == itemValue).isOpenChild =
        !this.selectNav.items.find((item) => item.value == itemValue)
          .isOpenChild;
    },
  },
  watch: {
    $route() {
      this.selectNav = this.nav.find((item) => item.value == this.$route.name);
      return this.selectNav;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css?family=Roboto");
@-webkit-keyframes come-in {
  0% {
    -webkit-transform: translatey(100px);
    transform: translatey(100px);
    opacity: 0;
  }
  30% {
    -webkit-transform: translateX(-50px) scale(0.4);
    transform: translateX(-50px) scale(0.4);
  }
  70% {
    -webkit-transform: translateX(0px) scale(1.2);
    transform: translateX(0px) scale(1.2);
  }
  100% {
    -webkit-transform: translatey(0px) scale(1);
    transform: translatey(0px) scale(1);
    opacity: 1;
  }
}
@keyframes come-in {
  0% {
    -webkit-transform: translatey(100px);
    transform: translatey(100px);
    opacity: 0;
  }
  30% {
    -webkit-transform: translateX(-50px) scale(0.4);
    transform: translateX(-50px) scale(0.4);
  }
  70% {
    -webkit-transform: translateX(0px) scale(1.2);
    transform: translateX(0px) scale(1.2);
  }
  100% {
    -webkit-transform: translatey(0px) scale(1);
    transform: translatey(0px) scale(1);
    opacity: 1;
  }
}
* {
  margin: 0;
  padding: 0;
}

html,
body {
  background: #eaedf2;
  font-family: "Roboto", sans-serif;
}

.floating-container {
  position: fixed;
  width: 100px;
  height: 100px;
  bottom: 0;
  right: 0;
  margin: 35px 25px;
}
.floating-container:hover {
  height: 300px;
}
.floating-container:hover .floating-button {
  box-shadow: 0 10px 25px rgba(44, 179, 240, 0.6);
  -webkit-transform: translatey(5px);
  transform: translatey(5px);
  -webkit-transition: all 0.3s;
  transition: all 0.3s;
}
.floating-container:hover .element-container .float-element:nth-child(1) {
  -webkit-animation: come-in 0.4s forwards 0.2s;
  animation: come-in 0.4s forwards 0.2s;
}
.floating-container:hover .element-container .float-element:nth-child(2) {
  -webkit-animation: come-in 0.4s forwards 0.4s;
  animation: come-in 0.4s forwards 0.4s;
}
.floating-container:hover .element-container .float-element:nth-child(3) {
  -webkit-animation: come-in 0.4s forwards 0.6s;
  animation: come-in 0.4s forwards 0.6s;
}
.floating-container .floating-button {
  position: absolute;
  width: 65px;
  height: 65px;
  background: #2cb3f0;
  bottom: 0;
  border-radius: 50%;
  left: 0;
  right: 0;
  margin: auto;
  color: white;
  line-height: 65px;
  text-align: center;
  font-size: 23px;
  z-index: 100;
  box-shadow: 0 10px 25px -5px rgba(44, 179, 240, 0.6);
  cursor: pointer;
  -webkit-transition: all 0.3s;
  transition: all 0.3s;
}
.floating-container .float-element {
  position: relative;
  display: block;
  border-radius: 50%;
  width: 50px;
  height: 50px;
  margin: 15px auto;
  color: white;
  font-weight: 500;
  text-align: center;
  line-height: 50px;
  z-index: 0;
  opacity: 0;
  -webkit-transform: translateY(100px);
  transform: translateY(100px);
}
.floating-container .float-element .material-icons {
  vertical-align: middle;
  font-size: 16px;
}
.floating-container .float-element:nth-child(1) {
  background: #42a5f5;
  box-shadow: 0 20px 20px -10px rgba(66, 165, 245, 0.5);
}
.floating-container .float-element:nth-child(2) {
  background: #4caf50;
  box-shadow: 0 20px 20px -10px rgba(76, 175, 80, 0.5);
}
.floating-container .float-element:nth-child(3) {
  background: #ff9800;
  box-shadow: 0 20px 20px -10px rgba(255, 152, 0, 0.5);
}

.nav-level-one {
  font-size: 20px !important;
  font-family: "KIMM_Bold";
  color: black;
  line-height: 55px !important;
  text-decoration-line: none;
}
.nav-level-two {
  font-size: 15px !important;
  font-family: "KIMM_Bold";
  color: black;
  line-height: 30px !important;
  text-decoration-line: none;
  margin-left: 20px;
}
/* 임의의 영역 생성 */
.nav-bar {
  height: calc(100vh - 100px);
  overflow-y: scroll;
}

/* 아래의 모든 코드는 영역::코드로 사용 */
.nav-bar::-webkit-scrollbar {
  width: 10px; /* 스크롤바의 너비 */
}

.nav-bar::-webkit-scrollbar-thumb {
  height: 30%; /* 스크롤바의 길이 */
  background: #217af4; /* 스크롤바의 색상 */

  border-radius: 10px;
}

.nav-bar::-webkit-scrollbar-track {
  background: rgba(33, 122, 244, 0.1); /*스크롤바 뒷 배경 색상*/
}
</style>
