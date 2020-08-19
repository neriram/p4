<template>
<v-app>
  <v-row justify="left">
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
    margin-top: 10px;
    margin-left: 10%;
    position: absolute

}

</style>