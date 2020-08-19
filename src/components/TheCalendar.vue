<template>
<v-app>
    <v-card id="cal" >
  <v-row justify="center">
    <v-date-picker v-model="picker"></v-date-picker>
  </v-row>
    </v-card>
</v-app>
</template>

<script>
  export default {
    data () {
      return {
        picker: new Date().toISOString().substr(0, 10),
      }
    },
  }
</script>

<style scoped>
/* #cal {
    margin-top: 10px;
    margin-left: 50%;
    display: inline-block;
   

} */

</style>