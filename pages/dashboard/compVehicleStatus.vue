<template>
  <div>
    <v-card-title>
      Vehicle
      <v-spacer />
      <span class="caption">
        <a href="#" style="text-decoration:none;">View Report</a>
      </span>
    </v-card-title>
    <v-list id="style-2" style="max-height:150px" class="scroll-y">
      <v-list-tile v-for="item in ListItems" :key="item.status">
        <v-list-tile-content>
          <v-list-tile-title>{{ item.status }}</v-list-tile-title>
        </v-list-tile-content>
        <v-list-tile-action>
          <v-avatar :color="item.color" size="18">
            <span class="white--text caption">{{ item.qty }}</span>
          </v-avatar>
        </v-list-tile-action>
      </v-list-tile>
    </v-list>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
@Component
export default class extends Vue {
  private ListItems = [
    {
      status: 'Active',
      qty: 12,
      color: 'green'
    },
    {
      status: 'In Active',
      qty: 5,
      color: 'blue'
    },
    {
      status: 'In Shop',
      qty: 9,
      color: 'yellow'
    },
    {
      status: 'Out Of Service',
      qty: 0,
      color: 'red'
    },
    {
      status: 'Sold',
      qty: 1,
      color: 'grey'
    }
  ]
}
</script>

<style scoped>
#style-2::-webkit-scrollbar-track {
  -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
  box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
  border-radius: 10px;
  background-color: #f5f5f5;
}

#style-2::-webkit-scrollbar {
  width: 12px;
  background-color: #f5f5f5;
}

#style-2::-webkit-scrollbar-thumb {
  border-radius: 10px;
  -webkit-box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
  box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
  background-color: grey;
}
</style>
