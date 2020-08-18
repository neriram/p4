<template>
  <v-app>
    <Header />
    <v-container>
    
      <v-row cols="12" sm="6" md="8">
        <!-- <v-card class="ma-4" outlined tile> -->
          
          <Carousel />
        <!-- </v-card> -->
      </v-row>
     
      <v-row cols="6" md="4">
        <!-- <v-card class="pa-2" outlined tile> -->
          <h1>bbBook: for all of baby's precious milestones</h1>
        <!-- </v-card> -->
      </v-row>
    </v-container>
  </v-app>
</template>


<script>
import Header from "../components/Header";
import Carousel from "../components/Carousel";

export default {
  name: "Home",
  components: {
    Header,
    Carousel
  }
};
</script>
<style scoped>
.tagline {
  color: red
}
</style>