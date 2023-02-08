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
              <h2 class="section-title font-weight-medium">{{ title }}</h2>
              <h2 class="section-title font-weight-medium" v-if="title == ''">
                비버의 일상일지
              </h2>
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
        <div v-if="title == ''">
          <v-row justify="center" style="padding-top: 40px">
            <v-img
              :src="require('@/assets/images/welcome.svg')"
              max-height="500"
              max-width="350"
            />
          </v-row>
          <v-row justify="center">
            <v-col cols="12" sm="10" md="9" lg="7">
              <div class="text-center">
                <h3 class="section-title font-weight-medium">
                  환영합니다! 비버입니다. 😊
                </h3>
                <p>왼쪽의 카테코리를 선택해주세요</p>
              </div>
            </v-col>
          </v-row>
        </div>
        <div v-else-if="data.length == 0">
          <v-row justify="center" style="padding-top: 40px">
            <v-img
              :src="require('@/assets/images/no_data.svg')"
              max-height="500"
              max-width="200"
            />
          </v-row>
          <v-row justify="center">
            <v-col cols="12" sm="10" md="9" lg="7">
              <div class="text-center">
                <h3 class="section-title font-weight-medium">
                  아직 작성된 글이 없습니다..ㅠㅠ
                </h3>
                <p>비버에게 빨리 쓰라고 재촉해주세요..!</p>
              </div>
            </v-col>
          </v-row>
        </div>

        <v-row v-else class="mt-13" justify="center">
          <div v-for="(item, idx) in data" :key="idx">
            <v-col cols="12" justify="center">
              <v-card elevation="3" class="blog-card overflow-hidden mb-15">
                <div style="padding: 20px">
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
      </v-container>
    </div>
  </div>
</template>
<script>
export default {
  name: "DailyPreview",
  props: {
    data: {
      type: Array,
      default: () => {},
    },
    title: {
      type: String,
      default: () => "Daily Note",
    },
  },
};
</script>
<style scoped>
.blog-component {
  font-family: "Cafe24Oneprettynight";
  text-decoration-line: none;
  padding-bottom: 0px;
}
</style>>
