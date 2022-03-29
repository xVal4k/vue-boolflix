<template>
  <div class="card">
    <h2>Titolo: {{ card.title }}</h2>
    <h2>Titolo Originale: {{ card.original_title }}</h2>
    <h3>Voto Medio: {{ card.vote_average }}</h3>
    <h3>Lingua Originale: {{ card.original_language }}</h3>
  </div>
</template>

<script>
/* esling-disable */
export default {
  name: 'CardFilm',
  props: {
    card: Object,
  },
};
</script>

<style scoped lang="scss">
  .card {
    padding: 1rem;
    background: black;
    color: white;
    width: calc(100% / 5 - 1rem);
    margin: .5rem;
    text-align: center;
  }
</style>
