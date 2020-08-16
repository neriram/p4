<template>
  <v-carousel 
  :show-arrows="false"
  cycle
  >
    <v-carousel-item
      v-for="(item,i) in items"
      :key="i"
      :src="item.src"
    ></v-carousel-item>
  </v-carousel>
</template>

<script>
  export default {
    data () {
      return {
        items: [
          {
            src: 'https://images.unsplash.com/photo-1512846947153-55eb89716f77?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=60',
          },
          {
            src: 'https://images.unsplash.com/photo-1537673156864-5d2c72de7824?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1955&q=80',
          },
          {
            src: 'https://images.unsplash.com/photo-1504151864552-57020b6b876b?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=800&q=60',
          },
          {
            src: 'https://images.unsplash.com/photo-1594172104231-f5ba30c28366?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80',
          },
        ],
      }
    },
  }
</script>
<style scoped>

</style>