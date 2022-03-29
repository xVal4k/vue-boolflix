<template>
  <header>
    <h1 class="logo">BOOLFLIX</h1>
    <div class="header-right">
      <label for="movie-search">
        <input
          v-model="strSearch"
          type="text"
          name="movie-search"
          id="movie-search"
          placeholder="Digita il titolo"
        />
      </label>
      <button id="btn-search" @click="generateCards">Cerca</button>
    </div>
  </header>
</template>

<script>
/* eslint-disable */
import axios from "axios";

export default {
  name: "HeaderBoolflix",
  data() {
    return {
      strSearch: "",
      arrMovies: [],
      arrSeries: [],
    };
  },
  methods: {
    generateCards() {
      axios
        .get(
          "https://api.themoviedb.org/3/search/movie?api_key=060663a1ee9fb81d34d744059a61645a&language=it-IT&query=" +
            this.strSearch)
        .then((response1) => {
          this.arrMovies = response1.data.results;
          this.$emit("movie-received", this.arrMovies);
        });
      axios
        .get(
          "https://api.themoviedb.org/3/search/tv?api_key=060663a1ee9fb81d34d744059a61645a&language=it-IT&query=" +
            this.strSearch)
        .then((response2) => {
          this.arrSeries = response2.data.results;
          this.$emit("serie-received", this.arrSeries);
        });
      this.strSearch = "";
    },
  },
};
</script>

<style scoped lang="scss">
h1 {
  color: red;
}

input,
#btn-search {
  height: 2rem;
  border-radius: 5px;
  border: solid 1px transparent;
}

input {
  padding: 0 0.5rem;
}

button {
  padding: 0 1.5rem;
  background: red;
  color: white;
  cursor: pointer;
}
</style>
