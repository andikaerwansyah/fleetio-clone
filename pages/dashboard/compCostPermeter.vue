<template>
  <div>
    <v-card-title>
      Cost Per Meter
      <v-spacer />
      <v-spacer />
      <span class="caption"
        ><a href="#" style="text-decoration:none;">View Report</a></span
      >
    </v-card-title>
    <div id="chart-cost-permeter"></div>
  </div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import * as Highcharts from 'highcharts'
@Component
export default class extends Vue {
  private aaa = ''
  mounted() {
    Highcharts.chart('chart-cost-permeter', {
      title: {
        text: ''
      },
      subtitle: {
        text: '',
        align: 'left'
      },

      yAxis: {
        title: {
          text: ''
        }
      },
      xAxis: {
        type: 'datetime'
      },

      plotOptions: {
        series: {
          label: {
            connectorAllowed: false
          },
          pointStart: Date.UTC(2010, 0, 1),
          pointInterval: 24 * 3600 * 1000 // one day
        }
      },
      chart: {
        height: 150
      },
      series: [
        {
          name: 'Cost/Mi',
          data: [0, 1, 0]
        }
      ] as any,

      responsive: {
        rules: [
          {
            condition: {
              maxWidth: 300,
              maxHeight: 150
            },
            chartOptions: {
              legend: {
                layout: 'horizontal',
                align: 'center',
                verticalAlign: 'bottom'
              }
            }
          }
        ]
      }
    })
  }
}
</script>
<style></style>
