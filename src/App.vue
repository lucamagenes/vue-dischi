<template>
  <div id="app">
    <SiteHeader title="Spotify" />
    <SiteMain />
    <SiteFooter copyright="Lorem" />
  </div>
</template>

<script>
import SiteHeader from "./components/SiteHeader.vue";
import SiteMain from "./components/SiteMain.vue";
import SiteFooter from "./components/SiteFooter.vue";

export default {
  name: "App",
  components: {
    SiteHeader,
    SiteMain,
    SiteFooter,
  },
};
</script>

<style lang="scss">
@import "../node_modules/bootstrap/scss/bootstrap";
@import "./assets/scss/common.scss";
</style>
