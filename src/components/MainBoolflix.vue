<template>
  <main>
    <div v-if="arrSerieName.length == 0"></div>
    <h1>Film</h1>
    <div class="movies">
      <card-film v-for="card in arrMovieName" :key="card.title" :card="card" />
    </div>
    <h1>Serie</h1>
    <div class="series">
      <card-serie v-for="card in arrSerieName" :key="card.title" :card="card" />
    </div>
  </main>
</template>

<script>
/* eslint-disable */

import CardFilm from "./CardFilm.vue";
import CardSerie from "./CardSerie.vue";

export default {
  name: 'MainBoolflix',
  components: {
    CardFilm,
    CardSerie,
  },
  props: {
    arrMovieName: Array,
    arrSerieName: Array,
  },
};
</script>

<style scoped lang="scss">
.movies,
.series {
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
}

h1 {
  margin: 3rem 0 2rem 0;
  text-align: center;
}
</style>
