<template>
  <v-app>
    <v-main>
      <v-container class="container">
        <Home />
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
import Home from './views/Home.vue'
export default {
  name: 'App',
  data: () => ({
    //
  }),
  components: {
    Home
  },
  created () {
    this.$vuetify.theme.dark = true
  },
};
</script>
<style lang="scss">
.container {
  border-left: 1px solid rgba(255, 255, 255, 0.7);
  border-right: 1px solid rgba(255, 255, 255, 0.7);
  padding: 40px;
}
</style>
