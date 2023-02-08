<template>
  <v-container class="py-0 fill-height">
    <!-- Logo -->
    <div class="banner-white-logo" v-if="$route.name == 'index'">
      <NLink class="text" nuxt to="/"> 비버의 홈페이지</NLink>
    </div>
    <div class="banner-white-logo" v-else>
      <NLink class="text" nuxt to="/"> {{ selectTitle.name }}</NLink>
    </div>
    <v-spacer></v-spacer>
    <v-btn class="d-block d-md-none" text @click="toggleClass()">
      <v-app-bar-nav-icon class="white--text" />
    </v-btn>
    <!-- Desktop view Navigation -->
    <div
      class="navigation"
      v-bind:class="[isActive ? 'd-block' : '']"
      @click="isActive = !isActive"
    >
      <ul class="navbar-nav">
        <li class="nav-item" text>
          <n-link class="nav-link" nuxt to="/profile"> Profile </n-link>
        </li>
        <li class="nav-item" text>
          <n-link class="nav-link" nuxt to="/tech"> Tech </n-link>
        </li>

        <li class="nav-item" text>
          <n-link class="nav-link" nuxt to="/contest"> Contest </n-link>
        </li>

        <li class="nav-item" text>
          <n-link class="nav-link" nuxt to="/project"> Project </n-link>
        </li>
        <li class="nav-item" text>
          <n-link class="nav-link" nuxt to="/activity"> Activity </n-link>
        </li>
        <li class="nav-item" text>
          <n-link class="nav-link" nuxt to="/edit"> Edit </n-link>
        </li>
        <li class="nav-item" text>
          <n-link class="nav-link" nuxt to="/life"> Life </n-link>
        </li>
        <li>
          <!-- login-regiter -->
          <v-btn
            small
            style="font-size: 15px; margin-left: 15px"
            color="white"
            nuxt
            target="_blank"
            elevation="0"
            href="https://mail.google.com/mail/u/0/?tab=rm&ogbl#inbox?compose=new"
          >
            Contact ME 💌
          </v-btn>
        </li>
      </ul>
    </div>
  </v-container>
</template>

<script>
export default {
  name: "HeaderNav",
  components: {},
  data() {
    return {
      isActive: false,
      attrs: "",
      on: "",
      titleList: [
        {
          name: "비버의 개발일지",
          value: "tech",
        },
        {
          name: "비버의 대회일지",
          value: "contest",
        },
        {
          name: "비버의 프로젝트",
          value: "project",
        },
        {
          name: "비버의 활동일지",
          value: "activity",
        },
        {
          name: "비버의 일상일지",
          value: "life",
        },
      ],
      selectTitle: {
        name: "비버의 개발일지",
        value: "tech",
      },
    };
  },
  methods: {
    toggleClass: function (event) {
      this.isActive = !this.isActive;
    },
  },
  mounted() {
    this.selectTitle = this.titleList.find(
      (item) => item.value == this.$route.name
    );
  },
  watch: {
    $route() {
      this.selectTitle = this.titleList.find(
        (item) => item.value == this.$route.name
      );
      return this.selectTitle;
    },
  },
};
</script>

<style>
</style>