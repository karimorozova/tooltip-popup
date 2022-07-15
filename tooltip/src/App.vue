<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <PopupTooltip/>
</template>

<script>
import PopupTooltip from './components/PopupTooltip.vue'

export default {
  name: 'App',
  components: {
    PopupTooltip
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
