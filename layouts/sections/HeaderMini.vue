<template>
  <div>
    <!-- -----------------------------------------------
          Start Header
    ----------------------------------------------- -->
    <v-app-bar
      app
      class="app-header position-relative navbar-light header1"
      flat
    >
      <v-container class="py-0 fill-height">
        <!-- Logo -->
        <div class="banner-logo">
          <NLink class="text" nuxt to="/"> 비버의 개발 일지</NLink>
        </div>

        <v-spacer></v-spacer>
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
            <li class="nav-item" text v-bind="attrs" v-on="on">
              <n-link class="nav-link" nuxt to="/profile"> Profile </n-link>
            </li>
            <li class="nav-item" text v-bind="attrs" v-on="on">
              <n-link class="nav-link" nuxt to="/tech"> Tech </n-link>
            </li>

            <li class="nav-item" text v-bind="attrs" v-on="on">
              <n-link class="nav-link" nuxt to="/contest"> Contest </n-link>
            </li>

            <li class="nav-item" text v-bind="attrs" v-on="on">
              <n-link class="nav-link" nuxt to="/project"> Project </n-link>
            </li>

            <v-menu open-on-hover offset-y>
              <template v-slot:activator="{ on, attrs }">
                <li class="nav-item" text v-bind="attrs" v-on="on">
                  <n-link class="nav-link" nuxt to="/activity">
                    Activity
                  </n-link>
                </li>
              </template>
              <v-list style="background-color:rgba(0, 0, 0, 0.3); ">
                <v-list-item
                  v-for="(item, index) in activityItems"
                  :key="index"
                >
                  <n-link
                    class="nav-link white--text"
                    style="text-decoration-line: none; align-items: center;"
                    nuxt
                    :to="item.url"
                  >
                    {{ item.title }}
                  </n-link>
                  <!-- <v-list-item-title
                    style="text-align: center;"
                    class="white--text"
                    >{{ item.title }}</v-list-item-title
                  > -->
                </v-list-item>
              </v-list>
            </v-menu>
            <v-menu open-on-hover offset-y>
              <template v-slot:activator="{ on, attrs }">
                <li class="nav-item" text v-bind="attrs" v-on="on">
                  <n-link class="nav-link" nuxt to="/basic-components">
                    Life
                  </n-link>
                </li>
              </template>
              <v-list style="background-color:rgba(0, 0, 0, 0.3);">
                <v-list-item v-for="(item, index) in lifeItems" :key="index">
                  <n-link
                    class="nav-link white--text"
                    style="text-decoration-line: none;"
                    nuxt
                    :to="item.url"
                  >
                    {{ item.title }}
                  </n-link>
                </v-list-item>
              </v-list>
            </v-menu>

            <li>
              <!-- login-regiter -->
              <v-btn
                small
                style="font-size: 15px; margin-left:15px;"
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
        { title: "Publish", url: "/publish" }
      ],
      lifeItems: [
        { title: "Daily", url: "/daily" },
        { title: "Review", url: "/review" },
        { title: "Hobby", url: "/hobby" }
      ],
      attrs: "",
      on: ""
    };
  },
  methods: {
    toggleClass: function(event) {
      this.isActive = !this.isActive;
    }
  }
};
</script>
