<template>
  <div class="card">
    <div class="image">
      <img :src="source + card.backdrop_path" :alt="card.title" />
    </div>
    <div class="text">
      <h2>{{ card.title }}</h2>
      <h3>({{ card.original_title }})</h3>
      <h4>Voto Medio: {{ card.vote_average }}</h4>
      <h4>Lingua Originale: {{ card.original_language }}</h4>
    </div>
  </div>
</template>

<script>
/* esling-disable */
export default {
  name: 'CardFilm',
  props: {
    card: Object,
  },
  data() {
    return {
      source: 'https://image.tmdb.org/t/p/w342',
    };
  },
};
</script>

<style scoped lang="scss">
.card {
  width: calc(100% / 5 - 1rem);
  height: 400px;
  padding: 2rem 1rem;
  background: black;
  color: white;
  margin: 0.5rem;
  text-align: center;
}

img {
  width: 100%;
}
</style>
