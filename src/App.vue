<template>
<v-app class='main'>
  <Home />
</v-app>
</template>

<script>
import Home from './components/Home';

export default {
  name: 'App',

  components: {
    Home,
  },

  data: () => ({
    //
  }),
};
</script>
<style scoped>
main {
  color: '#ffeb3b'
}
</style>