<template>
  <v-card
    class="mx-auto"
    max-width="400"
    id="profile"
  >
    <v-img
      class="white--text align-end"
      height="200px"
      src="@/assets/chuck.png"
    >
      <v-card-title>Chucky's bbBook</v-card-title>
    </v-img>

    <v-card-subtitle class="pb-0">Age: 9 months</v-card-subtitle>

    <v-card-text class="text--primary">
      <div>Newest milestone: standing</div>

      <div></div>
    </v-card-text>

    <v-card-actions>
      <v-btn
        color="orange"
        text
      >
        Share
      </v-btn>

      <v-btn
        color="orange"
        text
      >
        Explore
      </v-btn>
    </v-card-actions>
  </v-card>
</template>
<style scoped>
#profile{
    margin-top: 100px;
    
}
</style>