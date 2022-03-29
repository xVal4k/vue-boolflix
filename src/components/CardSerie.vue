<template>
  <div class="card">
    <div class="image">
      <img :src="source + card.backdrop_path" :alt="card.title" />
    </div>
    <div class="text">
      <h2>{{ card.name }}</h2>
      <h3>({{ card.original_name }})</h3>
      <h4>Voto Medio: {{ card.vote_average }}</h4>
      <lang-flag :iso="card.original_language" :squared="false" />
    </div>
  </div>
</template>

<script>
/* esling-disable */
import LangFlag from 'vue-lang-code-flags';

export default {
  name: 'CardSerie',
  components: {
    LangFlag,
  },
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

</style>
