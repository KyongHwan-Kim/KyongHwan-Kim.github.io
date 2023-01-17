<template>
  <div>
    <div class="blog-component mini-spacer">
      <v-container>
        <v-row justify="center">
          <v-col cols="12" md="7" lg="4">
            <v-card elevation="0" class="blog-card overflow-hidden mb-15">
              <div class="position-relative mb-15">
                <a href="#">
                  <v-img
                    :src="require('@/assets/images/blog/img1.jpg')"
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
                  >Learn from small things to create something bigger.</a
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
          <v-col cols="12" md="6" lg="4">
            <v-card elevation="0" class="blog-card overflow-hidden mb-15">
              <div class="position-relative mb-15">
                <a href="#">
                  <v-img
                    :src="require('@/assets/images/blog/img1.jpg')"
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
                  >Learn from small things to create something bigger.</a
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
          <v-col cols="12" md="6" lg="4">
            <v-card elevation="0" class="blog-card overflow-hidden mb-15">
              <div class="position-relative mb-15">
                <a href="#">
                  <v-img
                    :src="require('@/assets/images/blog/img2.jpg')"
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
                  >New Seminar on Newest Food Recipe from World’s Best</a
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
                  >You should have eagle’s eye on new trends and techonogies</a
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
  </div>
</template>
<script>
export default {
  name: "Blog",
  data() {
    return {};
  },
  methods: {}
};
</script>
