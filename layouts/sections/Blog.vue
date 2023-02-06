<template>
  <div>
    <v-carousel
      cycle
      height="400"
      hide-delimiter-background
      show-arrows-on-hover
    >
      <v-carousel-item v-for="(slide, i) in slides" :key="i">
        <div class="blog-component mini-spacer">
          <v-container>
            <v-row justify="center">
              <v-col cols="12" md="6" lg="4">
                <v-card elevation="0" class="blog-card overflow-hidden mb-15">
                  <div class="position-relative mb-15">
                    <a href="#">
                      <v-img
                        :src="require('@/assets/images/blog/img3.jpg')"
                        alt="blog"
                        class="blog-img"
                      />
                    </a>
                    <div class="date-badge bg-info-grediant">
                      Oct <span>23</span>
                    </div>
                  </div>
                  <div>
                    <a
                      href="#"
                      class="
                        blog-title
                        text-decoration-none
                        font-weight-medium font-18
                      "
                      >You should have eagle’s eye on new trends and
                      techonogies</a
                    >
                    <p class="mt-10 mb-10">
                      Business Park, Opp. Corns Sam Restaurant, New Yoark, US
                    </p>
                    <a
                      href="#"
                      class="
                        text-themecolor
                        linking
                        text-decoration-none
                        d-flex
                        align-center
                      "
                    >
                      Learn More <i class="mdi mdi-arrow-right"></i>
                    </a>
                  </div>
                </v-card>
              </v-col>
            </v-row>

            <!-- -----------------------------------------------
            End Blog
        ----------------------------------------------- -->
          </v-container>
        </div>
      </v-carousel-item>
    </v-carousel>
  </div>
</template>
<script>
export default {
  name: "Blog",
  data() {
    return {
      colors: [
        "indigo",
        "warning",
        "pink darken-2",
        "red lighten-1",
        "deep-purple accent-4",
      ],
      slides: ["First", "Second", "Third", "Fourth", "Fifth"],
    };
  },
  methods: {},
};
</script>
