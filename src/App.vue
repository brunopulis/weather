<template>
  <div id="app">
    <Header msg="Weather API"></Header>
    <Weather></Weather>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Weather from './components/Weather.vue'

export default {
  name: 'app',
  components: {
    Header,
    Weather
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 0;
}
</style>
