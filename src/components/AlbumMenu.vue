<template>
    <div class="menu flex flex-col items-center justify-center gap-3 mx-auto">
      <MenuButton v-for="index in 1" :key="index" :change-background="changeBackground" />
    </div>
  </template>
  
  <script>
  import MenuButton from './MenuButton.vue'
  
  export default {
    name: 'AlbumMenu',
    components: {
      MenuButton
    },
    props: {
      changeBackground: Function
    }
  }
  </script>
  
<style scoped>
</style>