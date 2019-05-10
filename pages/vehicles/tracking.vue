<template>
  <div id="map-wrap" style="height: 100%;z-index:0;">
    <no-ssr>
      <l-map :zoom="13" :center="[-6.251442, 106.79091]">
        <comp-show-list-car></comp-show-list-car>
        <v-layout column fill-height>
          <v-spacer></v-spacer>
          <comp-detail-tracking
            style="z-index:13 !important;"
          ></comp-detail-tracking>
        </v-layout>

        <l-tile-layer
          style="z-index:-100 !important"
          url="http://{s}.tile.osm.org/{z}/{x}/{y}.png"
        >
        </l-tile-layer>
        <l-marker :lat-lng="[-6.251442, 106.79091]"></l-marker>
      </l-map>
    </no-ssr>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import { LMap, LTileLayer, LMarker } from 'vue2-leaflet'
import compShowListCar from './components/compShowListCar.vue'
import compDetailTracking from './components/compDetailTracking.vue'

if (process.client) {
  require('vue2-leaflet')
}

@Component({
  components: {
    LMap,
    LTileLayer,
    LMarker,
    compShowListCar,
    compDetailTracking
  },
  metaInfo: {
    title: 'Live Tracking - Black Box'
  }
})
export default class Tracking extends Vue {
  private mounted() {}
}
</script>

<style>
.leaflet-pane {
  z-index: 0 !important;
}
</style>
