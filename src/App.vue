<template>
  <div id="app">
    <img src="./assets/cloud.png" alt="">
    <h1>What's the Weather?</h1>
    <WeatherChecker></WeatherChecker>
  </div>
</template>

<script>
import WeatherChecker from './components/WeatherChecker.vue'

export default {
  name: 'App',
  components: {
    WeatherChecker,
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
