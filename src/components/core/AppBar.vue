<template>
<div>

  <v-app-bar app flat>
    <v-app-bar-nav-icon @click="drawer=!drawer" />

    <v-container class="mx-auto py-0">
      <v-row align="center">
        <v-img :src="require('@/assets/logo.png')" class="mr-5" contain height="48" width="48" max-width="48" />

        <!-- <v-btn v-for="(link, i) in links" :key="i" v-bind="link" class="hidden-sm-and-down" text
          @click="onClick($event, link)">
          {{ link.text }}
        </v-btn> -->
        <v-btn class="d-none d-lg-flex d-xl-none" text to="/">Home</v-btn>
        <v-btn class="d-none d-lg-flex d-xl-none" text to="/about">About</v-btn>
        <v-btn class="d-none d-lg-flex d-xl-none" text to="/blog">Blog</v-btn>

        <v-spacer />

        <v-text-field append-icon="mdi-magnify" flat hide-details solo-inverted style="max-width: 300px;" />
      </v-row>
    </v-container>
  </v-app-bar>
    <v-navigation-drawer v-model="drawer" app >
      <v-list>
        <v-list-item two-line :class="'px-0'">
          <v-list-item-avatar>
            <v-icon>person</v-icon>
          </v-list-item-avatar>
          <v-list-item-content>
            <v-list-item-title>Application</v-list-item-title>
            <v-list-item-subtitle>Subtext</v-list-item-subtitle>
          </v-list-item-content>
        </v-list-item>

        <v-divider></v-divider>
        <v-list-item v-for="(link,index) in links" :key="index" router :to="link.href">
          <v-list-item-content>
            <v-list-item-title>{{ link.text }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
</div>
</template>

<script>
  // Utilities
  // import Drawer from './Drawer.vue'
  // import {
  //   mapGetters,
  //   mapMutations,
  // } from 'vuex'

  export default {
    // components: {
    //   drawer: Drawer
    // },
    name: 'CoreAppBar',
    data() {
      return {
        drawer: false,
        links: [{
            text: 'HOME',
            href: '/',
          },
          {
            text: 'ABOUT',
            href: '/about'
          },
          {
            text: 'BLOG',
            href: '/blog'
          },
        ]
      }

    },


  //   methods: {
  //     ...mapMutations(['toggleDrawer']),
  //     onClick(e, item) {
  //       e.stopPropagation()

  //       if (item.to || !item.href) return

  //       this.$vuetify.goTo(item.href.endsWith('!') ? 0 : item.href)
  //     },
  //   },
  }

</script>

<style scoped>
  .v-btn--active {
    background-color: rgba(222, 181, 20, 0.885);
  }

</style>
