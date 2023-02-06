<template>
  <div>
    <div class="blog-component mini-spacer">
      <v-container>
        <!-- -----------------------------------------------
            Start Blog Text
        ----------------------------------------------- -->
        <v-row justify="center">
          <v-col cols="12" sm="10" md="9" lg="7">
            <div class="text-center">
              <h2 class="section-title font-weight-medium">일상 블로그</h2>
              <p>저의 일상 블로그는 네이버 블로그에서 보실 수 있습니다!</p>
              <p>더 보고 싶은 게시물을 클릭하시면 네이버 블로그로 이동해요!</p>
              <a
                href="https://blog.naver.com/dolkys123"
                class="
                  blog-title
                  text-decoration-none
                  font-weight-medium font-18
                "
                >블로그 바로가기</a
              >
            </div>
          </v-col>
        </v-row>

        <v-row class="mt-13" justify="center">
          <div v-for="(item, idx) in blogs" :key="idx">
            <v-col cols="12">
              <v-card elevation="0" class="blog-card overflow-hidden mb-15">
                <div class="position-relative mb-15">
                  <div class="date-badge bg-info-grediant">
                    {{ item.pubDate._text.split(" ")[2] }}
                    <span>{{ item.pubDate._text.split(" ")[1] }}</span>
                  </div>
                </div>
                <div>
                  <a
                    :href="item.link._text"
                    class="
                      blog-title
                      text-decoration-none
                      font-weight-medium font-18
                    "
                    >{{ item.title._cdata }}</a
                  >
                  <p class="mt-10 mb-10">
                    {{ item.description._cdata }}
                  </p>
                  <a
                    :href="item.link._text"
                    class="
                      text-themecolor
                      linking
                      text-decoration-none
                      d-flex
                      align-center
                    "
                  >
                    Read More <i class="mdi mdi-arrow-right"></i>
                  </a>
                </div>
              </v-card>
            </v-col>
          </div>
        </v-row>

        <!-- -----------------------------------------------
            End Blog
        ----------------------------------------------- -->
      </v-container>
    </div>
  </div>
</template>
<script>
import convert from "xml-js";

export default {
  name: "DailyPreview",
  data() {
    return {
      blogs: [],
    };
  },
  mounted() {
    this.getBlogs();
    for (let blog of this.blogs) {
      this.$axios.get(blog.link._text).then((html) => {
        let $ = cheerio.load(html);
        const data = $("head > meta:nth-child(8)").text();
        console.log(data);
      });
    }
  },
  methods: {
    getBlogs() {
      this.$axios.get("/blog/dolkys123.xml").then((res) => {
        let xml = res.data;
        let json = convert.xml2json(xml, { compact: true });
        let data = JSON.parse(json);
        this.blogs = data.rss.channel.item.filter(
          (item) => item.category._cdata === "일상"
        );
      });
    },
  },
};
</script>
