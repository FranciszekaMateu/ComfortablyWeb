<template>
  <div class="h-full w-full" :style="{ backgroundImage: `url(${backgroundImage})` }">
    <MusicReproductor/>
  </div>
</template>

<script>
import MusicReproductor from './components/MusicReproductor.vue'
export default {
  name: 'App',
  components: {
    MusicReproductor
  },
  data() {
    return {
      backgroundImage: 'https://i.pinimg.com/736x/9c/ce/ed/9cceedb85aa7fdbe60f3512da07ee5bf.jpg',
    }
  },
  methods: {
    updateBackground(newColor) {
      this.backgroundImage = newColor;
    }
  }
}
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  height: 100vh;
  
  
  
}
div {
  background-size: cover; 
  background-position: center; 
  background-repeat: no-repeat;
  transition: background-image 0.5s ease-in-out; /* Añade esta línea */
}

</style>
