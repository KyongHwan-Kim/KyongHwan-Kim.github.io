<template>
  <div class="banner-wrapper">
    <v-container>
      <!-- -----------------------------------------------
            Start Banner
        ----------------------------------------------- -->
      <v-row justify="center">
        <v-col
          v-if="width > 767"
          cols="12"
          md="7"
          lg="6"
          class="d-flex align-center"
        >
          <div class="text-center text-md-left typewriter">
            <h1 class="banner-title font-weight-bold white--text">
              # echo "Hello World!"
            </h1>
            <h4 class="banner-subtitle white--text font-weight-regular">
              안녕하세요. <br />
              비버의 개발 일지에 오신 것을 환영합니다. <br />
              <br />
              저의 작고 소중한 홈페이지입니다. <br />
              피드백은 언제나 환영입니다 ╰(@'''🔻'''@)╯<br />
            </h4>
          </div>
        </v-col>
        <v-col v-else cols="align-self">
          <div class="text-center text-md-left">
            <h1 class="banner-title font-weight-bold white--text">
              # echo "Hello World!"
            </h1>
            <h4 class="banner-subtitle white--text font-weight-regular">
              안녕하세요. <br />
              비버의 개발 일지에 오신 것을 환영합니다. <br />
              <br />
              저의 작고 소중한 홈페이지입니다. <br />
              피드백은 언제나 환영입니다 ╰(@'''🔻'''@)╯<br />
            </h4>
          </div>
        </v-col>
        <v-col cols="12" md="5" lg="6">
          <v-img
            :src="require('@/assets/images/landingpage/banner-img.png')"
            alt="banner"
          />
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>
<script>
export default {
  name: "Banner",
  data() {
    return {
      width: 0,
      height: 0,
    };
  },
  mounted() {
    // console.log("ready...");
    window.addEventListener("resize", this.handleResize);
    this.handleResize();
  },
  beforeDestroy() {
    // console.log("beforeDestroy...");
    window.removeEventListener("resize", this.handleResize);
  },
  methods: {
    handleResize(event) {
      this.width = window.innerWidth;
      this.height = window.innerHeight;
    },
  },
};
</script>
<style scoped>
.typewriter h1 {
  overflow: hidden; /* Ensures the content is not revealed until the animation */
  border-right: solid black; /* The typwriter cursor */
  white-space: nowrap; /* Keeps the content on a single line */
  margin: 0 auto; /* Gives that scrolling effect as the typing happens */
  animation: typing 3.5s steps(21, end), blink-caret 0.75s step-end infinite;
}

/* The typing effect */
@keyframes typing {
  from {
    width: 0;
  }
  to {
    width: 100%;
  }
}

/* The typewriter cursor effect */
@keyframes blink-caret {
  from,
  to {
    border-color: transparent;
  }
  50% {
    border-color: black;
  }
}
</style>
