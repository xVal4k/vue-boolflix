<template>
  <div id="app">
    <HeaderBoolflix />
    <MainBoolflix />
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
};
</script>

<style lang="scss">
@import './assets/styles/style.scss'
</style>
