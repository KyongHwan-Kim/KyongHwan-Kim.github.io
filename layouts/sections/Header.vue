<template>
  <div>
    <!-- -----------------------------------------------
          Start Header
    ----------------------------------------------- -->
    <v-app-bar app absolute class="app-header" flat elevate-on-scroll>
      <v-container class="py-0 fill-height">
        <!-- Logo -->
        <div class="banner-logo">
          <NLink class="text" nuxt to="/"> 비버의 개발 일지</NLink>
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
    </v-app-bar>
    <!-- -----------------------------------------------
          End Header
    ----------------------------------------------- -->
  </div>
</template>

<script>
export default {
  name: "Header",
  components: {},
  data() {
    return {
      isActive: false,
      activityItems: [
        { title: "Club", url: "/club" },
        { title: "Publish", url: "/publish" },
      ],
      lifeItems: [
        { title: "Daily", url: "/daily" },
        { title: "Review", url: "/review" },
        { title: "Hobby", url: "/hobby" },
      ],
      attrs: "",
      on: "",
    };
  },
  methods: {
    toggleClass: function (event) {
      this.isActive = !this.isActive;
    },
  },
};
</script>
