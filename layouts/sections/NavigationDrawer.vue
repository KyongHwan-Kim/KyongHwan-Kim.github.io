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
      <v-list dense v-for="item in selectNav.items" :key="item.value">
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
        <v-list-item-group
          mandatory
          v-if="item.child.length > 0 && item.isOpenChild"
        >
          <div v-for="child in item.child" :key="child.value">
            <v-list-item @click="changePage(item.value, child.value)">
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
                { title: "ALL", value: "all" },
                { title: "2023", value: "2023" },
                { title: "2022", value: "2022" },
              ],
            },
            {
              title: "Think About",
              value: "think",
              isOpenChild: true,
              child: [
                { title: "ALL", value: "all" },
                { title: "2023", value: "2023" },
                { title: "2022", value: "2022" },
              ],
            },
            {
              title: "Book",
              value: "book",
              isOpenChild: true,
              child: [
                { title: "ALL", value: "all" },
                { title: "Tech", value: "tech" },
                { title: "Essay", value: "essay" },
                { title: "Personal Growth", value: "growth" },
              ],
            },
            {
              title: "Hobby",
              value: "hobby",
              isOpenChild: true,
              child: [
                { title: "ALL", value: "all" },
                { title: "Whiskey", value: "whiskey" },
                { title: "Cycle", value: "cycle" },
                { title: "Work Out", value: "work-out" },
              ],
            },
          ],
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
      this.selectNav.items.find((item) => item.value == itemValue).isOpenChild =
        !this.selectNav.items.find((item) => item.value == itemValue)
          .isOpenChild;
    },
    changePage(parentPath, childPath) {
      this.navDetailItems.push(parentPath);
      this.navDetailItems.push(childPath);
    },
  },
};
</script>

<style>
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