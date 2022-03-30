<template>
  <div class="card">
    <div class="card-front">
      <img :src="source + card.poster_path" :alt="card.title" />
    </div>
    <div class="card-back">
      <h2>
        Titolo: <span class="grey">{{ card.title }}</span>
      </h2>
      <h2>
        Titolo originale: <span class="grey">{{ card.original_title }}</span>
      </h2>
      <h3 class="trama">
        <span class="grey">{{ card.overview }}</span>
      </h3>
      <h4>
        <span>Voto Medio: </span>
        <span v-for="star in card.vote_average" :key="star">&#9733;</span>
        <span v-for="Emptystar in (5 - card.vote_average)" :key="Emptystar">&#9734;</span>
      </h4>
      <p>
        Lingua originale:
        <lang-flag :iso="card.original_language" :squared="false" />
      </p>
    </div>
  </div>
</template>

<script>
/* esling-disable */
import LangFlag from 'vue-lang-code-flags';

export default {
  name: 'CardFilm',
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

<style scoped lang="scss"></style>
