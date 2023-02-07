<template>
  <div>
    <NavgationDrawer />
    <v-container>
      <DailyPreview
        v-if="this.routeDetail[0] == 'daily'"
        :category="routeDetail"
      />
    </v-container>
  </div>
</template>

<script>
export default {
  name: "Life",
  props: {
    routeDetail: {
      type: Array,
      default: ["daily", "all"],
    },
  },
  data() {
    return {
      route: "Life",
    };
  },
  components: {
    DailyPreview: () => import("@/layouts/sections/life/DailyPreview"),
    NavgationDrawer: () => import("@/layouts/sections/NavigationDrawer"),
  },
  mounted() {},
  watch: {
    routeDetail() {
      console.log(this.routeDetail);
    },
  },
  methods: {
    changeRoute(route) {
      this.route = route;
    },
  },
};
</script>
