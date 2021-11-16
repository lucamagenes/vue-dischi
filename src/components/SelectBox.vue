<template>
  <div class="selectBox">
    <div class="filterGenres">
      <label for="" class="form-label">Filtra per genere</label>
      <select
        class="form-control"
        name=""
        id=""
        @change.prevent="$emit('filter-genere', selected)"
        v-model="selected"
      >
        <option v-for="genre in genres" :key="genre.value" :value="genre.value">
          {{ genre.value }}
        </option>
      </select>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selected: "Tutti",
      genres: [
        { value: "Tutti" },
        { value: "Jazz" },
        { value: "Metal" },
        { value: "Pop" },
        { value: "Rock" },
      ],
    };
  },
};
</script>

<style lang="scss">
.selectBox {
  margin-right: 4rem;
  margin-top: 5rem;

  .filterGenres {
    width: 130px;
  }
}
</style>