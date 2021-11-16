<template>
  <div class="container">
    <SelectBox @filter-genere="selectByGenere" />
    <div class="row justify-content-center" v-if="!loading">
      <div
        class="col-md-2"
        v-for="album in getFilteredGenere"
        :key="album.poster"
      >
        <div class="albums text-center">
          <img :src="album.poster" :alt="album.author" class="img-fluid" />
          <h3>{{ album.title }}</h3>
          <p>{{ album.author }}</p>
          <small>{{ album.year }} </small>
        </div>
      </div>
    </div>
    <div class="loading text-center pt-5" v-else>Loading ...</div>
  </div>
</template>

<script>
import axios from "axios";
import SelectBox from "./SelectBox.vue";

export default {
  components: {
    SelectBox,
  },
  data() {
    return {
      albums: [],
      loading: true,
      error: "",
      musicGenre: "",
    };
  },
  mounted() {
    setTimeout(this.callApi, 1000);
  },
  methods: {
    callApi() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((r) => {
          console.log(r.data.response);
          this.albums = r.data.response;
          this.loading = false;
        })
        .catch((e) => {
          console.log(e, "OPS!");
        });
    },
    selectByGenere(genre) {
      console.log(genre);

      this.musicGenre = genre;
    },
  },
  computed: {
    getFilteredGenere() {
      if (this.musicGenre === "Tutti") {
        return this.albums;
      }
      const filteredGenres = this.albums.filter((album) => {
        return album.genre.includes(this.musicGenre);
      });
      return filteredGenres;
    },
  },
};
</script>

<style lang="scss">
@import "../assets/scss/common.scss";

.row {
  padding-top: 5rem;

  .albums {
    background-color: $secondary-color-brand;
    color: $text-secondary-color;
    padding: 1rem;
    height: 370px;
    margin-bottom: 1rem;
    h3 {
      color: $text-primary-color;
      margin-top: 1rem;
    }
    p {
      margin-bottom: 0;
    }
  }
}
</style>