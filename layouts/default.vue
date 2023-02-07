<template>
  <v-app dark>
    <Header />
    <v-main>
      <nuxt />
    </v-main>
    <Footer />
    <FAB />
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
    Footer: () => import("@/layouts/sections/Footer"),
    FAB: () => import("@/components/FAB"),
  },
};
</script>

<style>
</style>
