<template>
  <div id="app">
    <notifications group="map" />
    <mapa/>
  </div>
</template>

<script>
import Mapa from './components/Mapa.vue'

export default {
  name: 'app',
  components: {
    Mapa
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