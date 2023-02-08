<template>
  <div>
    <NavgationDrawer
      :navList="navList"
      @parentPath="getParentPath"
      @childPath="getChildPath"
    />
    <div id="md-html" class="markdown-body">
      <techMd />
    </div>
  </div>
</template>

<script>
import techList from "@/data/techList.json";

export default {
  name: "Tech",
  data() {
    return {
      items: techList,
      navList: {
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
      // page: techContent
    };
  },
  components: {
    NavgationDrawer: () => import("@/layouts/sections/NavigationDrawer"),
  },
};
Header;
</script>
<style scoped>
::v-deep .v-treeview {
  font-family: "KIMM_Bold";
}
::v-deep .v-sheet {
  position: fixed;
  top: 20;
  /* width: 100% */
  left: 0;
  right: 0;
}
</style>
