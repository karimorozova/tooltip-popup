<template lang="pug">
div
  img(alt="Vue logo" src="./assets/logo.png")
  IconButton(:popup-text="'Hello friend'" :popupSide="'right'")
    span K
</template>

<script>
import IconButton from './components/IconButton.vue'

export default {
  name: 'App',
  components: {
    IconButton
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
