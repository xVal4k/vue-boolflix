<template>
  <main>
    <card-film v-for="card in arrMovieName" :key="card.title" :card="card" />
  </main>
</template>

<script>
/* eslint-disable */

import CardFilm from "./CardFilm.vue";

export default {
  name: "MainBoolflix",
  components: {
    CardFilm,
  },
  props: {
    arrMovieName: Array,
  },
};
</script>

<style scoped lang="scss"></style>
