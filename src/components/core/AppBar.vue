<template>
  <v-app-bar app flat>
    <v-app-bar-nav-icon class="hidden-md-and-up" @click="toggleDrawer" />

    <v-container class="mx-auto py-0">
      <v-row align="center">
        <v-img :src="require('@/assets/logo.png')" class="mr-5" contain height="48" width="48" max-width="48"
          @click="$vuetify.goTo(0)" />

        <!-- <v-btn v-for="(link, i) in links" :key="i" v-bind="link" class="hidden-sm-and-down" text
          @click="onClick($event, link)">
          {{ link.text }}
        </v-btn> -->
        <v-btn  class="hidden-sm-and-down" text to="/">Home</v-btn>
        <v-btn  class="hidden-sm-and-down" text to="/about">About</v-btn>
        <v-btn  class="hidden-sm-and-down" text to="/blog">Blog</v-btn>

        <v-spacer />

        <v-text-field append-icon="mdi-magnify" flat hide-details solo-inverted style="max-width: 300px;" />
      </v-row>
    </v-container>
  </v-app-bar>
</template>

<script>
  // Utilities
  import {
    mapGetters,
    mapMutations,
  } from 'vuex'

  export default {
    name: 'CoreAppBar',

    computed: {
      ...mapGetters(['links']),
    },

    methods: {
      ...mapMutations(['toggleDrawer']),
      onClick(e, item) {
        e.stopPropagation()

        if (item.to || !item.href) return

        this.$vuetify.goTo(item.href.endsWith('!') ? 0 : item.href)
      },
    },
  }

</script>

<style scoped>
.v-btn--active{
  background-color: rgba(222, 181, 20, 0.885);
}
</style>