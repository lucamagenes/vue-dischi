<template>
  <header>
    <div class="container">
      <div class="logo">
        <img src="../assets/Spotify_logo_without_text.svg" alt="" />
      </div>
    </div>
  </header>
</template>

<script>
export default {};
</script>

<style lang='scss'>
@import "../assets/scss/common.scss";

header {
  background-color: $secondary-color-brand;

  .logo {
    width: 100%;
    padding: 1rem 0;
    img {
      height: 40px;
    }
  }
}
</style>