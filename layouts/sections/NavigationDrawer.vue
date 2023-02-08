<template>
  <v-navigation-drawer
    v-if="$route.name != 'index' && $route.name != 'profile'"
    hide-overlay
    fixed
    clipped
    bottom
    permanent
    style="
      padding-top: 85px;
      transform: translateX(0%);
      width: 300px;
      max-height: calc(100vh);
      opacity: 1;
    "
  >
    <div class="nav-bar">
      <v-list dense v-for="item in navList.items" :key="item.value">
        <v-list-item-group mandatory>
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
        <v-list-item-group v-if="item.child.length > 0 && item.isOpenChild">
          <div v-for="child in item.child" :key="child.value">
            <v-list-item
              v-if="child.isSelect"
              color="#5c9bf4"
              @click="changePage(item.value, child)"
            >
              <v-list-item-title class="nav-level-two">{{
                child.title
              }}</v-list-item-title>
            </v-list-item>
            <v-list-item
              v-else
              color="white"
              @click="changePage(item.value, child)"
            >
              <v-list-item-title class="nav-level-two">{{
                child.title
              }}</v-list-item-title>
            </v-list-item>
          </div>
        </v-list-item-group>
      </v-list>
    </div>
  </v-navigation-drawer>
</template>

<script>
export default {
  props: {
    navList: {
      type: Object,
      default: () => {},
    },
  },
  data() {
    return {
      nav: [
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
      ],
      selectNav: {
        title: "",
        value: "",
        items: [],
      },
      navDetailItems: [],
    };
  },
  mounted() {
    this.selectNav = this.nav.find((item) => item.value == this.$route.name);
  },
  methods: {
    changeOpenChild(itemValue) {
      this.navList.items.find((item) => item.value == itemValue).isOpenChild =
        !this.navList.items.find((item) => item.value == itemValue).isOpenChild;
    },
    changePage(parentPath, child) {
      for (let e of this.navList.items) {
        for (let c of e.child) {
          c.isSelect = false;
        }
      }
      child.isSelect = true;
      this.$emit("selectParams", parentPath, child.value);
    },
  },
};
</script>

<style>
::v-deep .v-list-item--active {
  background-color: #5c9bf4 !important;
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