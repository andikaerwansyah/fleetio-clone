<template>
  <div>
    <v-card-title>
      Vehicle Assignments
    </v-card-title>
    <v-layout row>
      <v-flex xs6 column>
        <p class="text-xs-center headline green--text">10</p>
        <p class="text-xs-center">Assigned</p>
      </v-flex>
      <v-flex xs6 column>
        <p class="text-xs-center headline orange--text">3</p>
        <p class="text-xs-center">Assigned</p>
      </v-flex>
    </v-layout>
  </div>
</template>

<script>
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class extends Vue {}
</script>

<style></style>
