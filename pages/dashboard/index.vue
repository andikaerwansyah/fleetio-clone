<template>
  <v-container grid-list-xl>
    <v-layout row wrap>
      <v-flex xs12 sm3 column>
        <v-card class="bra-5 pa-2 mb-3">
          <comp-vehicle-status></comp-vehicle-status>
        </v-card>
        <v-card class="bra-5 pa-2">
          <comp-cost-permeter></comp-cost-permeter>
        </v-card>
      </v-flex>
      <v-flex xs12 sm6>
        <v-card class="bra-5 pa-2">
          <comp-last-meter></comp-last-meter>
        </v-card>
      </v-flex>
      <v-flex xs12 sm3 column>
        <v-card class="bra-5 pa-2 mb-3">
          <comp-vehicle-assignment></comp-vehicle-assignment>
        </v-card>
        <v-card class="bra-5 pa-2">
          <comp-fuel-cost></comp-fuel-cost>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import compLastMeter from './compLastMeter.vue'
import compVehicleStatus from './compVehicleStatus.vue'
import compCostPermeter from './compCostPermeter.vue'
import compVehicleAssignment from './compVehicleAssignment.vue'
import compFuelCost from './compFuelCost.vue'

@Component({
  components: {
    compLastMeter,
    compVehicleStatus,
    compCostPermeter,
    compVehicleAssignment,
    compFuelCost
  },
  metaInfo: {
    title: 'Dashboard - Black Box'
  }
})
export default class extends Vue {
  mounted() {}
}
</script>

<style>
.bra-5 {
  border-radius: 8px !important;
}
</style>
