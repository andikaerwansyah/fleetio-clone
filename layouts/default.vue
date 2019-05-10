<template>
  <v-app>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
      width="240"
      class="grey lighten-3"
    >
      <v-layout column fill-height>
        <v-toolbar flat color="grey lighten-3">
          <v-list class="pa-0">
            <v-list-tile avatar @click="showMenu = true">
              <v-list-tile-avatar color="blue" size="35">
                <v-icon color="white">mdi-account</v-icon>
              </v-list-tile-avatar>
              <v-list-tile-content>
                <v-layout column justify-center>
                  <span class="caption font-weight-bold">
                    Company Name
                    <v-icon small>mdi-chevron-down</v-icon>
                  </span>
                  <p class="caption mb-0">User Name</p>
                </v-layout>
              </v-list-tile-content>
            </v-list-tile>
            <v-menu
              v-model="showMenu"
              :position-x="x"
              :position-y="y"
              absolute
              offset-y
            >
              <v-list>
                <v-list-tile v-for="(item, index) in menus" :key="index">
                  <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                </v-list-tile>
              </v-list>
            </v-menu>
          </v-list>
        </v-toolbar>
        <v-list dense>
          <v-list-tile
            v-for="item in sidebarMenus"
            :key="item.title"
            :to="item.to"
            route
            exact
          >
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title class="font-weight-bold">{{
                item.title
              }}</v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
        <v-spacer />
        <v-list>
          <v-list-tile>
            <v-list-tile-action v-if="miniVariant === true">
              <v-icon size="28" @click.stop="miniVariant = !miniVariant"
                >mdi-chevron-right</v-icon
              >
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title class="text-xs-right">
                <v-icon size="28" @click.stop="miniVariant = !miniVariant"
                  >mdi-chevron-left</v-icon
                >
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-layout>
    </v-navigation-drawer>
    <v-toolbar :clipped-left="clipped" fixed app color="white">
      <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
      <v-img
        :src="require('../static/black-box-logo.png')"
        contain
        height="55"
        position="left left"
      />
      <v-spacer />
      <v-btn flat icon color="grey" outline>
        <v-icon>mdi-help</v-icon>
      </v-btn>
    </v-toolbar>
    <v-content>
      <nuxt />
    </v-content>
  </v-app>
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'

@Component
export default class DefaultLayout extends Vue {
  private clipped = false
  private drawer = true
  private fixed = false
  private miniVariant = false
  private showMenu = false
  private x = 50
  private y = 50
  private sidebarMenus = [
    {
      icon: 'mdi-speedometer',
      title: 'Dashboard',
      to: '/dashboard'
    },
    {
      icon: 'mdi-crosshairs-gps',
      title: 'Tracking',
      to: '/vehicles/tracking'
    },
    {
      icon: 'mdi-office-building',
      title: 'Management',
      to: '/management'
    },
    {
      icon: 'mdi-file-cabinet',
      title: 'Report',
      to: '/report'
    }
  ]
  private menus = [{ title: 'Biling & Subscriptions' }, { title: 'Sign Out' }]
}
</script>
