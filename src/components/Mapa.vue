<template>
  <div class="hello">
    <h1>Austria Map</h1>
    <p>
      Please click a state to view state properties
    </p>
    <div>
      <map-container v-on:map-clicked="onMapClick"/>
    </div>
  </div>
</template>

<script>
import MapContainer from './MapContainer'
export default {
  name: 'Mapa',
  components: {
    MapContainer
  },
  props: {
    msg: String
  },
  methods: {
    onMapClick: function(attr){
      this.$notify({
        group: 'map',
        title: 'State clicked',
        text: `You clicked on state with id: ${attr.mapId} and title: ${attr.title}`
      });
    }
  }
}
</script>