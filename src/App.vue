<template>
  <v-app>
    <core-app-bar />

    <core-drawer />

    <core-view />

    <core-footer />

    <core-cta />
  </v-app>
</template>

<script>
  export default {
    name: 'App',

    components: {
      CoreCta: () => import('@/components/core/Cta'),
      CoreDrawer: () => import('@/components/core/Drawer'),
      CoreFooter: () => import('@/components/core/Footer'),
      CoreAppBar: () => import('@/components/core/AppBar'),
      CoreView: () => import('@/components/core/View'),
    },
  }

</script>

<style>
  @font-face {
    font-family: "Hurricane";
    src: local("Hurricane_Regular"),
      url(./assets/fonst/Hurricane_Regular.ttf) format("truetype");
  }

  @font-face {
    font-family: "Barlow";
    src: local("Barlow_Light"),
      url(./assets/fonst/Barlow_Light.ttf) format("truetype");
  }

  @font-face {
    font-family: "Cardo_Regular";
    src: local("Cardo_Regular"),
      url(./assets/fonst/Cardo_Regular.ttf) format("truetype");
  }

</style>
