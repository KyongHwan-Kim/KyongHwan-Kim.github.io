<template>
  <div>
    <!-- -----------------------------------------------
          Start Header
    ----------------------------------------------- -->
    <v-app-bar
      app
      absolute
      class="app-header"
      flat
      elevate-on-scroll
      v-if="$route.name == 'index'"
    >
      <HeaderNav />
    </v-app-bar>
    <v-app-bar app class="app-header bg-dark header1" flat v-else>
      <HeaderNav />
    </v-app-bar>
    <!-- -----------------------------------------------
          End Header
    ----------------------------------------------- -->
  </div>
</template>

<script>
export default {
  name: "Header",
  components: { HeaderNav: () => import("@/components/HeaderNav") },
};
</script>
