<template>
  <table>
    <tr>
      <th class="caption"></th>
      <th class="caption">Name</th>
      <th class="caption">License Plate</th>
    </tr>
    <tr>
      <td>
        <v-checkbox value="false"></v-checkbox>
      </td>
      <td class="caption">
        Honda City
      </td>
      <td class="caption">B 3343 WKU</td>
    </tr>
    <tr>
      <td>
        <v-checkbox value="false"></v-checkbox>
      </td>
      <td class="caption">
        Suzuki Terios
      </td>
      <td class="caption">B 7877 UY</td>
    </tr>
    <tr>
      <td>
        <v-checkbox value="false"></v-checkbox>
      </td>
      <td class="caption">
        Toyota Kijang
      </td>
      <td class="caption">L 8897 IUP</td>
    </tr>
  </table>
</template>
<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
@Component
export default class extends Vue {}
</script>

<style>
table {
  font-family: arial, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

td,
th {
  text-align: left;
  padding: 0px;
}

/* tr:nth-child(even) {
  background-color: #dddddd;
} */
</style>
