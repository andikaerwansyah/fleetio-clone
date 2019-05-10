<template>
  <v-card color="transparent" light flat tile>
    <v-window v-model="onboarding">
      <v-window-item v-for="n in length" :key="`card-${n}`">
        <v-card flat color="transparent" height="250">
          <v-container grid-list-xs>
            <v-layout align-center justify-center fill-height tag="v-card-text">
              <v-flex xs12 sm4>
                <v-card class="bra-5">
                  <v-card-title class="title">
                    Detail
                  </v-card-title>
                  <v-card-text>
                    <p>
                      Name : Toyota Xpander
                    </p>
                    <p>
                      License Plate : H 8729 KOI
                    </p>
                    <p>
                      Color : Red Metalic
                    </p>
                    <p>
                      Type : MPV
                    </p>
                  </v-card-text>
                </v-card>
              </v-flex>
            </v-layout>
          </v-container>
        </v-card>
      </v-window-item>
    </v-window>

    <v-card-actions class="justify-space-between">
      <v-btn icon color="white" @click="prev">
        <v-icon>mdi-chevron-left</v-icon>
      </v-btn>
      <v-item-group v-model="onboarding" class="text-xs-center" mandatory>
        <v-item v-for="n in length" :key="`btn-${n}`">
          <v-btn
            slot-scope="{ active, toggle }"
            :input-value="active"
            icon
            @click="toggle"
          >
            <v-icon>mdi-record</v-icon>
          </v-btn>
        </v-item>
      </v-item-group>
      <v-btn icon color="white" @click="next">
        <v-icon>mdi-chevron-right</v-icon>
      </v-btn>
    </v-card-actions>
  </v-card>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class extends Vue {
  private length = 3
  private onboarding = 0
  private itemDetails = [
    {
      name: 'Mitsubishi Xpander',
      licensePlate: 'B 1234 AUY',
      color: 'Red Metalic',
      type: 'MPV'
    }
  ]

  private next() {
    this.onboarding =
      this.onboarding + 1 === this.length ? 0 : this.onboarding + 1
  }
  private prev() {
    this.onboarding =
      this.onboarding - 1 < 0 ? this.length - 1 : this.onboarding - 1
  }
}
</script>

<style>
.bra-5 {
  border-radius: 8px;
}
</style>
