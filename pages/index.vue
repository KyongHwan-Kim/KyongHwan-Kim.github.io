<template>
  <div>
    <Banner />
    <Divider :title="divider.title" :subtitle="divider.subtitle" />
    <Blog />

    <ComingSoon />
  </div>
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

  data() {
    return {
      divider: {
        title: "Recent Posts",
        subtitle:
          "I think the best learning is to write something that others can easily understand.",
      },
    };
  },
  components: {
    Banner: () => import("@/layouts/sections/Banner"),
    Divider: () => import("@/layouts/sections/Divider"),
    Blog: () => import("@/layouts/sections/Blog"),
    ComingSoon: () => import("@/components/shared/coming-soon/ComingSoon"),
    AllCustomComponents: () =>
      import("@/components/custom/AllCustomComponents"),
  },
};
</script>
