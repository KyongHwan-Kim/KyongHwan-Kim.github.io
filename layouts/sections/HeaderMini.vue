<template>
  <div>
    <!-- -----------------------------------------------
          Start Header
    ----------------------------------------------- -->
    <v-app-bar app class="app-header bg-dark header1" flat outlined>
      <v-container class="py-0 fill-height justify-center">
        <!-- Logo -->
        <v-btn class="d-block d-md-none" text @click="toggleClass()">
          <v-app-bar-nav-icon />
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
  name: "Header1",
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
      nav: [
        {
          title: "비버의 개발 일지",
          value: "tech",
          items: [
            {
              title: "Back-end",
              value: "back-end",
              child: [
                { title: "Back-end", value: "back-end" },
                { title: "Back-end", value: "back-end" },
                { title: "Back-end", value: "back-end" },
              ],
            },
            {
              title: "Back-end",
              value: "back-end",
              child: [
                { title: "Back-end", value: "back-end" },
                { title: "Back-end", value: "back-end" },
                { title: "Back-end", value: "back-end" },
              ],
            },
            { title: "Back-end", value: "back-end" },
          ],
        },
        {
          title: "비버의 대회 일지",
          value: "contest",
          items: [],
        },
        {
          title: "비버의 프로젝트",
          value: "project",
          items: [],
        },
        {
          title: "비버의 활동 일지",
          value: "activity",
          items: [],
        },
        {
          title: "비버의 일상 일지",
          value: "life",
          items: [],
        },
      ],
      navRoute: "",
      selectNav: {},
    };
  },
  methods: {
    toggleClass: function (event) {
      this.isActive = !this.isActive;
    },
  },
};
</script>
