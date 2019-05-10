<template>
  <div class="text-xs-center">
    <v-menu
      v-model="menu"
      :close-on-content-click="false"
      :nudge-width="200"
      offset-x
    >
      <template v-slot:activator="{ on }">
        <v-btn
          large
          class="mt-5"
          color="blue-grey"
          dark
          small
          absolute
          right
          top
          fab
          v-on="on"
        >
          <v-icon>mdi-car</v-icon>
        </v-btn>
      </template>

      <v-card>
        <v-card-title>
          <v-text-field
            hide-details
            prepend-icon="search"
            single-line
            placeholder="Search"
          ></v-text-field>
        </v-card-title>

        <v-divider></v-divider>
        <v-card-text>
          <table-cars></table-cars>
        </v-card-text>
        <v-card-actions>
          <v-btn
            class="text-none mx-auto"
            flat
            color="blue-grey"
            @click="menu = false"
          >
            <v-icon>mdi-car</v-icon> Minimize
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-menu>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import tableCars from './compTableCars.vue'
@Component({
  components: {
    tableCars
  }
})
export default class extends Vue {
  private fav = true
  private menu = false
  private message = false
  private hints = true
}
</script>

<style></style>
