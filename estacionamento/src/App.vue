<template>
  <div id="app">
    <Parking/>
  </div>
</template>

<script>
import Parking from './components/Parking.vue'

export default {
  name: 'app',
  components: {
    Parking
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
