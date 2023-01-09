<template>
  <v-app dark>
    <!--v-if="$route.name!=='login'"-->
    <Header v-if="$route.name == 'index'" />
    <HeaderMini v-else />
    <v-main>
      <nuxt />
    </v-main>
    <Footer />
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
          content: "안녕하세요 비버입니다. 아니지 저스틴입니다."
        }
      ]
    };
  },
  components: {
    Header: () => import("@/layouts/sections/Header"),
    HeaderMini: () => import("@/layouts/sections/HeaderMini"),
    Footer: () => import("@/layouts/sections/Footer")
  },
  methods: {}
};
</script>

<style></style>
