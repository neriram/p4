<template>
  <v-app id="home">
    <v-container>
      <v-layout row>
        <v-flex md8>
          <v-card>
            <v-row cols="12" sm="6" md="8">
              <Carousel />
            </v-row>
          </v-card>
        </v-flex>
        <v-flex md4>
        <!-- <v-row cols="6" md="4"> -->
          <v-row class="tagline"><span>bbBook:</span> for all of baby's precious milestones</v-row>
          <div class="text-center">
            <v-btn class="btn" rounded color="primary" dark to="/register">Join Now</v-btn>
          </div>
        <!-- </v-row> -->
      </v-flex>
      </v-layout>
    </v-container>
  </v-app>
</template>


<script>
import Carousel from "../components/Carousel";

export default {
  name: "Home",
  components: {
    Carousel
  }
};
</script>
<style scoped>
#home {
  margin: 150px;
}
.tagline {
  color: #fc6b03;
  font-size: 2em;
  display: inline-block;
  text-align: center;
  padding-top: 50%;
  padding-left: 10%;
}
.tagline span {
  color: #00bcd4 
}
.btn {
  margin-top: 25px;
}
</style>