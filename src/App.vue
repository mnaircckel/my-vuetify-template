<template>
<v-app light>
  <v-navigation-drawer persistent :clipped="clipped" v-model="drawer">
    <v-list>
      <v-list-tile v-for="(item, i) in items" :key="i" value="true" :href="item.href">
        <v-list-tile-action>
          <v-icon light v-html="item.icon"></v-icon>
        </v-list-tile-action>
        <v-list-tile-content>
          <v-list-tile-title v-text="item.title"></v-list-tile-title>
        </v-list-tile-content>
      </v-list-tile>
    </v-list>
  </v-navigation-drawer>
  <v-toolbar fixed>
    <v-toolbar-side-icon @click.native.stop="drawer = !drawer"></v-toolbar-side-icon>
    <v-toolbar-title v-text="title"></v-toolbar-title>
    <v-spacer></v-spacer>
    </v-btn>
  </v-toolbar>
  <main>
    <v-container fluid>
      <v-slide-y-transition mode="out-in">
        <v-layout column align-center>
        </v-layout>
      </v-slide-y-transition>
    </v-container>
  </main>
  <v-footer fixed>
    <span>&copy; 2017</span>
  </v-footer>
</v-app>
</template>

<script>
export default {
  data() {
    return {
      // Layout
      clipped: true,
      drawer: true,
      items: [{
        icon: 'home',
        title: 'Home',
        href: '/'
      }],
      right: true,
      title: 'Website Name'
      // Data
    }
  }
}
</script>

<style lang="stylus">
  @import './stylus/main'
</style>
