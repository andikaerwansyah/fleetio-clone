<template>
  <div id="chart-last-meter"></div>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import * as Highcharts from 'highcharts'
@Component
export default class extends Vue {
  private aaa = ''
  mounted() {
    Highcharts.chart('chart-last-meter', {
      title: {
        text: ''
      },
      subtitle: {
        text: 'Latest meter reading',
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
      legend: {
        layout: 'horizontal',
        align: 'center',
        verticalAlign: 'bottom'
      },

      plotOptions: {
        series: {
          label: {
            connectorAllowed: false
          },
          pointStart: Date.UTC(2010, 0, 1),
          pointInterval: 24 * 3600 * 1000 // one days
        }
      },

      series: [
        {
          name: 'Miles',
          data: [43934, 52503, 57177, 69658, 97031, 119931, 137133, 154175]
        },
        {
          name: 'Kilometers',
          data: [24916, 24064, 29742, 29851, 32490, 30282, 38121, 40434]
        },
        {
          name: 'Hours',
          data: [11744, 17722, 16005, 19771, 20185, 24377, 32147, 39387]
        }
      ] as any,

      responsive: {
        rules: [
          {
            condition: {
              maxWidth: 300
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
