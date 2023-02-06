<template>
  <div>
    <div id="md-html" class="markdown-body">
      <techMd />
    </div>
    <v-container>
      <BannerText />
      <Banner1 />
      <FormBannerText />
      <FormBanner1 />

      <FeatureText />
      <Feature1 />
      <Feature2 />
      <Feature3 />
      <PortfolioText />
      <Portfolio />
      <ContactText />
      <Contact />
    </v-container>
  </div>
</template>

<script>
import techList from "@/data/techList.json";
import Header from "../layouts/sections/Header.vue";

export default {
  name: "AllCustomComponents",
  data() {
    return {
      items: techList,
      // page: techContent
    };
  },
  components: {
    HeaderText: () => import("@/components/custom/header/HeaderText"),
    BannerText: () => import("@/components/custom/banner/BannerText"),
    FeatureText: () => import("@/components/custom/features/FeatureText"),
    PricingText: () => import("@/components/custom/pricing/PricingText"),
    TeamText: () => import("@/components/custom/team/TeamText"),
    ContactText: () => import("@/components/custom/contact/ContactText"),
    TestimonialText: () =>
      import("@/components/custom/testimonial/TestimonialText"),
    C2aText: () => import("@/components/custom/c2a/C2aText"),
    PortfolioText: () => import("@/components/custom/portfolio/PortfolioText"),
    FormBannerText: () =>
      import("@/components/custom/form-banner/FormBannerText"),
    Header1: () => import("@/components/custom/header/Header1"),
    Header2: () => import("@/components/custom/header/Header2"),
    Banner1: () => import("@/components/custom/banner/Banner1"),
    Banner2: () => import("@/components/custom/banner/Banner2"),
    Feature1: () => import("@/components/custom/features/Feature1"),
    Feature2: () => import("@/components/custom/features/Feature2"),
    Feature3: () => import("@/components/custom/features/Feature3"),
    FormBanner1: () => import("@/components/custom/form-banner/FormBanner1"),
    Portfolio: () => import("@/components/custom/portfolio/Portfolio"),
    Pricing: () => import("@/components/custom/pricing/Pricing"),
    Team: () => import("@/components/custom/team/Team"),
    Testimonial: () => import("@/components/custom/testimonial/Testimonial"),
    Blog: () => import("@/components/custom/blogs/Blog"),
    C2a1: () => import("@/components/custom/c2a/C2a1"),
    C2a2: () => import("@/components/custom/c2a/C2a2"),
    Contact: () => import("@/components/custom/contact/Contact"),
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
