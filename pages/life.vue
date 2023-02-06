<template>
  <div>
    <v-container>
      <DailyPreview v-if="this.route == 'Life'" />
    </v-container>
  </div>
</template>

<script>
export default {
  name: "Life",

  data() {
    return {
      route: "Life",
      list: [
        { value: "Life", text: "Life" },
        { value: "Think", text: "Think" },
        { value: "Review", text: "Review" },
        { value: "Book", text: "Book" },
        { value: "Wikey", text: "Wikey" },
      ],
    };
  },
  components: {
    DailyPreview: () => import("@/layouts/sections/life/DailyPreview"),
  },
};
</script>
