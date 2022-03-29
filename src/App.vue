<template>
  <div id="app">
    <HeaderBoolflix
      @cards-received="arrMovies = $event"
    />
    <MainBoolflix
      :arr-movie-name="arrMovies"
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
    }
  },
};
</script>

<style lang="scss">
@import './assets/styles/style.scss'
</style>
