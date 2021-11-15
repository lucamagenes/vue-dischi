<template>
  <div id="app">
    <SiteHeader title="Spotify" />
    <SiteMain />
  </div>
</template>

<script>
import SiteHeader from "./components/SiteHeader.vue";
import SiteMain from "./components/SiteMain.vue";

export default {
  name: "App",
  components: {
    SiteHeader,
    SiteMain,
  },
};
</script>

<style lang="scss">
@import "../node_modules/bootstrap/scss/bootstrap";
@import "./assets/scss/common.scss";
</style>
