<template>
  <v-app>
    <v-app-bar app clipped-left>
      <!-- <v-toolbar-title>Application</v-toolbar-title> -->
    </v-app-bar>
    <v-main>
      <v-container>
        <router-view></router-view>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  data: () => ({
    //
  }),
  created () {
    this.$vuetify.theme.dark = true
  },
};
</script>
