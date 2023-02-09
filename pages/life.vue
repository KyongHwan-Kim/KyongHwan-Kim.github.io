<template>
  <div>
    <NavgationDrawer :navList="navList" @selectParams="setComponent" />
    <v-container>
      <DailyPreview :data="detailData" :title="detailTitle" />
    </v-container>
  </div>
</template>

<script>
import convert from "xml-js";
import setting from "@/api/setting.json";
export default {
  name: "Life",
  data() {
    return {
      navList: {
        title: "비버의 일상일지",
        value: "life",
        items: [
          {
            title: "Daily",
            value: "Daily",
            isOpenChild: true,
            child: [
              { title: "ALL", value: "all", isSelect: false },
              { title: "2023", value: "2023", isSelect: false },
              { title: "2022", value: "2022", isSelect: false },
            ],
          },
          {
            title: "Think About",
            value: "Think About",
            isOpenChild: true,
            child: [
              { title: "ALL", value: "all", isSelect: false },
              { title: "2023", value: "2023", isSelect: false },
              { title: "2022", value: "2022", isSelect: false },
            ],
          },
          {
            title: "Book",
            value: "Book",
            isOpenChild: true,
            child: [
              { title: "ALL", value: "all", isSelect: false },
              { title: "Tech", value: "tech", isSelect: false },
              { title: "Essay", value: "essay", isSelect: false },
              { title: "Personal Growth", value: "growth", isSelect: false },
            ],
          },
          {
            title: "Hobby",
            value: "Hobby",
            isOpenChild: true,
            child: [
              { title: "ALL", value: "all", isSelect: false },
              { title: "Whiskey", value: "whiskey", isSelect: false },
              { title: "Cycle", value: "cycle", isSelect: false },
              { title: "Work Out", value: "work-out", isSelect: false },
            ],
          },
        ],
      },
      blogs: [],
      detailData: [],
      detailTitle: "",
    };
  },
  mounted() {
    this.getBlogs();
  },
  components: {
    DailyPreview: () => import("@/layouts/sections/life/DailyPreview"),
    NavgationDrawer: () => import("@/layouts/sections/NavigationDrawer"),
  },
  methods: {
    setComponent(category, child) {
      this.detailTitle = category;
      this.detailData = this.blogs.filter(
        (item) => item.category._cdata === category
      );
      if (category === "Daily") {
        if (child !== "all") {
          this.detailData = this.detailData.filter((item) =>
            item.title._cdata.includes(child)
          );
        }
      } else if (category === "Think About") {
        if (child !== "all") {
          this.detailData = this.detailData.filter((item) =>
            item.pubDate._text.includes(child)
          );
        }
      }
      //TODO: Filter Logic
      else if (category === "Book") {
        if (child !== "all") {
          this.detailData = this.detailData.filter((item) =>
            item.pubDate._text.includes(child)
          );
        }
      }
      //TODO: Filter Logic
      else if (category === "Hobby") {
        if (child !== "all") {
          this.detailData = this.detailData.filter((item) =>
            item.pubDate._text.includes(child)
          );
        }
      }
    },
    getBlogs() {
      if (setting.API_ENV === "development") {
        this.$axios.get("/blog/dolkys123.xml").then((res) => {
          let xml = res.data;
          let json = convert.xml2json(xml, { compact: true });
          let data = JSON.parse(json);
          this.blogs = data.rss.channel.item;
        });
      } else if (setting.API_ENV === "production") {
        this.$axios
          .get("https://rss.blog.naver.com/dolkys123.xml", {
            headers: {
              "Access-Control-Allow-Origin": "http://localhost:3000/",
              "Access-Control-Allow-Methods":
                "GET,PUT,POST,DELETE,PATCH,OPTIONS",
            },
          })
          .then((res) => {
            let xml = res.data;
            let json = convert.xml2json(xml, { compact: true });
            let data = JSON.parse(json);
            this.blogs = data.rss.channel.item;
          });
      }
    },
  },
};
</script>
