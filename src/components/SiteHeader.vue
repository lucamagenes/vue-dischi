<template>
  <header>
    <div class="logo">
      <img src="../assets/Spotify_logo_without_text.svg" alt="" />
    </div>
  </header>
</template>

<script>
export default {};
</script>

<style lang='scss'>
@import "../assets/scss/common.scss";

.logo {
  width: 100%;
  padding: 1rem 2rem;
  background-color: $secondary-color-brand;
  img {
    height: 40px;
  }
}
</style>