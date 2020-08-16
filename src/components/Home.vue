<template>
  <div>
    <Header />
    <v-container>
    
      <v-col cols="12" sm="6" md="8">
        <!-- <v-card class="ma-4" outlined tile> -->
          
          <Carousel />
        <!-- </v-card> -->
      </v-col>
     
      <v-row cols="6" md="4">
        <!-- <v-card class="pa-2" outlined tile> -->
          <h1 class="tagline">bbBook: for all of baby's precious milestones</h1>
        <!-- </v-card> -->
      </v-row>
    </v-container>
  </div>
</template>


<script>
import Header from "./Header";
import Carousel from "./Carousel";

export default {
  name: "Home",
  components: {
    Header,
    Carousel
  }
};
</script>
<style scoped>
</style>