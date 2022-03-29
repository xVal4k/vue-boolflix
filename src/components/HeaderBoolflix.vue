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
    };
  },
  methods: {
    generateCards() {
      axios
        .get(
          "https://api.themoviedb.org/3/search/movie?api_key=060663a1ee9fb81d34d744059a61645a&language=it-IT&query=" +
            this.strSearch
        )
        .then((response) => {
          this.arrMovies = response.data.results;
          this.$emit("cards-received", this.arrMovies);
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
