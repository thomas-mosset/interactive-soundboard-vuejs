<template>
  <SoundBoard />
</template>

<script>
import SoundBoard from './components/SoundBoard.vue'

export default {
  name: 'App',
  components: {
    SoundBoard,
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;700&display=swap');

#app {
  font-family: 'Montserrat', sans-serif;
  color: #054fb9;
}
</style>
