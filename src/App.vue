<template>
<v-app color="#ffeb3b">
  <div id="app">
    <TheNavbar />
    <router-view/>
  </div> 
</v-app>
</template>

<script>
import TheNavbar from '@/components/TheNavbar'
export default {
  components: {
    TheNavbar
  }
}
</script>
<style lang="scss">

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin: 0
  
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
