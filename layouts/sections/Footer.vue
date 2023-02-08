<template>
  <!-- -----------------------------------------------
        Start Footer
  ----------------------------------------------- -->
  <v-footer class="footer">
    <v-container>
      <v-row justify="center" class="py-0">
        <!-- -----------------------------------------------
        First Column
      ----------------------------------------------- -->
        <v-col cols="auto" sm="12" md="12" lg="3" class="px-xs-0">
          <h4 class="font-weight-regular font-18">Profile</h4>
          <p class="mt-10">Age : 24, Male</p>
          <p class="mt-5">Edu :</p>
          <p style="font-size: 13px">
            Donig Bachelor of Science <br />in Electronics and Informaion
            Engineering <br />at Sejong University
          </p>
          <p class="mt-5">MBTI : ESTJ</p>
        </v-col>
        <!-- -----------------------------------------------
        Second Column
      ----------------------------------------------- -->

        <!-- -----------------------------------------------
        Third Column
      ----------------------------------------------- -->
        <v-col cols="12" sm="12" md="12" lg="3" class="px-xs-0">
          <h4 class="font-weight-regular font-18">Email</h4>
          <p class="mt-10 mb-0">Gmail : kyounghwan1989@gmail.com</p>
          <p class="mt-10 mb-0">Naver : <br />dolkys123@naver.com</p>
        </v-col>
        <!-- -----------------------------------------------
        Fourth Column
      ----------------------------------------------- -->
        <v-col cols="12" sm="12" md="12" lg="2" class="px-xs-0">
          <h4 class="font-weight-regular font-18">Social</h4>

          <div class="social-icons mt-10">
            <a href="https://github.com/KyongHwan-Kim">
              <i class="mdi mdi-github"></i>
            </a>
            <!-- <a href="#">
              <i class="mdi mdi-youtube"></i>
            </a> -->
            <a href="https://www.instagram.com/kkenghwan/">
              <i class="mdi mdi-instagram"></i>
            </a>
          </div>
        </v-col>
      </v-row>
      <v-row justify="center" style="margin-top: 0px">
        <div class="footer-bottom-bar font-14" style="margin-top: 0px">
          <div class="d-block d-md-flex align-center">
            <p>All Rights Reserved by kyounghwan-kim</p>
          </div>
        </div>
      </v-row>
    </v-container>
  </v-footer>
  <!-- -----------------------------------------------
        End Footer
  ----------------------------------------------- -->
</template>

<script>
export default {
  name: "Footer",
  data() {
    return {
      data: [],
    };
  },
  components: {},
};
</script>
 