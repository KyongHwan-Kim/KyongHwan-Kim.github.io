<template>
  <div class="mini-spacer bg-extra-light">
    <v-container>
      <v-row justify="center">
        <v-col cols="12" sm="10" md="9" lg="7">
          <div class="text-center">
            <h2 class="ui-title font-weight-bold">{{ title }}</h2>
            <p>{{ subtitle }}</p>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: "Recent Posts"
    },
    subtitle: {
      type: String,
      default:
        "Here you can check Demos we created you can easily use it. Its quite easy to Create your own dream website & dashboard in No-time."
    }
  },
  data() {
    return {};
  }
};
</script>
