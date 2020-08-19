<template>
<v-app>
    <h3 class="date"></h3>
  <v-row justify="center">
    <v-date-picker id="cal" v-model="picker"></v-date-picker>
  </v-row>
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
#cal {
    margin-top: 20px;
    margin-left: 50%
}
.date{
    margin-top: 150px;
    margin-left: 50%
}
</style>