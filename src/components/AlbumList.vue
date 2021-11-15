<template>
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-md-2" v-for="album in albums" :key="album.poster">
        <div class="albums text-center">
          <img :src="album.poster" :alt="album.author" class="img-fluid" />
          <h3>{{ album.title }}</h3>
          <p>{{ album.author }}</p>
          <small>{{ album.year }} </small>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      albums: [],
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((r) => {
        console.log(r.data.response);
        this.albums = r.data.response;
      })
      .catch((e) => {
        console.log(e, "OPS!");
      });
  },
};
</script>

<style>
</style>