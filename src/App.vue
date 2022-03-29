<template>
  <div id="app">
    <HeaderBoolflix
      @movie-received="arrMovies = $event"
      @serie-received="arrSeries = $event"
    />
    <MainBoolflix
      :arr-movie-name="arrMovies"
      :arr-serie-name="arrSeries"
    />
  </div>
</template>

<script>
/* eslint-disable */

import HeaderBoolflix from './components/HeaderBoolflix.vue';
import MainBoolflix from './components/MainBoolflix.vue';

export default {
  name: 'App',
  components: {
    HeaderBoolflix,
    MainBoolflix
  },
  data () {
    return {
      arrMovies: null,
      arrSeries: null,
    }
  },
};
</script>

<style lang="scss">
@import './assets/styles/style.scss';
</style>
