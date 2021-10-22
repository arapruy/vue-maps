<template>
  <div class="hello">
    <v-card v-if="show" elevation="2">
      ola
    </v-card>
      <map-container v-on:map-clicked="onMapClick"/>
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
  data: () => ({
    show: false,
  }),

  methods: {
    onMapClick: function(){
      this.show = true
      }
    }
  /**
  methods: {
    onMapClick: function(attr){
      this.$notify({
        group: 'map',
        title: 'State clicked',
        text: `You clicked on state with id: ${attr.mapId} and title: ${attr.title}`
      });
    }
  }**/
}
</script>