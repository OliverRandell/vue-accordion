<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <LucindaRandell msg="Welcome to Your Vue.js App"/> -->
    <MediaResponses />
  </div>
</template>

<script>
// import LucindaRandell from './components/LucindaRandell.vue'
import MediaResponses from './components/MediaResponses.vue'

export default {
  name: 'app',
  components: {
    //LucindaRandell,
    MediaResponses
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
