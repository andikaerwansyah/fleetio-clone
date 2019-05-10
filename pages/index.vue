<template>
  <v-container grid-list-xs>
    <div class="text-xs-center">
      <v-progress-circular
        :size="30"
        color="primary"
        indeterminate
      ></v-progress-circular>
    </div>
  </v-container>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class Index extends Vue {
  mounted() {
    this.$router.push({ path: '/dashboard' })
  }
}
</script>
