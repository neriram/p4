<template>
    <v-app-bar
    id="bar"
      absolute
      color='#ffeb3b'
      elevate-on-scroll
      scroll-target="#scrolling-techniques-7"
    >
      <img src='../assets/Book.png' height="50px" to="/home">
      
      <v-toolbar-title class="logo"><span class="font-weight-bold">bbBook</span></v-toolbar-title>
      <v-spacer></v-spacer>
      <!-- <v-btn color='#ffeb3b' to="/login"> -->
      
      <router-link class="link" to="/">Home</router-link>
      <router-link class="link" to="/book">Book</router-link>
      <router-link class="link" to="/login">Login</router-link>
      <!-- <v-icon>mdi-account-circle</v-icon> -->
      <router-link class="link" to="/register">Register</router-link>
      
      <!-- <router-view/> -->
            <!-- </v-btn> -->

    </v-app-bar>
</template>
<style scoped>
#bar {
 color:#00bcd4 ;
 font-family: Verdana, Geneva, Tahoma, sans-serif;
 
 display: inline;
}

.logo {
  font-weight: bold;
  font-size: 50px;
  margin: 10px
}
.link {
display: flex;
justify-content: space-around;
padding-right: 5%;
text-decoration: none;
}
</style>