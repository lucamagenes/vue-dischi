<template>
  <main>
    <AlbumList />
  </main>
</template>

<script>
import AlbumList from "./AlbumList.vue";

export default {
  components: {
    AlbumList,
  },
};
</script>

<style lang="scss">
@import "../assets/scss/common.scss";

main {
  color: $text-primary-color;
}
</style>