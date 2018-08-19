<template>
  <div class="container-fluid">
    <div class="row">
      <div class="col-md-9" style="padding-left: 0">
        <map-loader
          :map-config="mapConfig"
          apiKey="AIzaSyCdsCZwgVbKBnvwqtPQ8Mqcv5P0lNzuxs8"
        >
          <template v-for="marker in markers">
            <child-marker
              :position="marker"
            />
          </template>
        </map-loader>
      </div>
      <div class="col-md-3">
        <h3>{{this.name}}</h3>

      </div>
    </div>
  </div>
</template>

<script>
import MapLoader from "./MapLoader.vue"
import ChildMarker from './ChildMarker'

export default {
  props: {
    markers: Array
  },

  data(){
    return {
      name: this.name,
      mapConfig: {
        zoom: 17,
        center: this.markers[0],
        zoomControl: true,
        mapTypeControl: false,
        scaleControl: true,
        streetViewControl: true,
        rotateControl: false,
        fullscreenControl: false
      }
    }
  },
  components: {

    MapLoader,
    ChildMarker,
  }
}
</script>

