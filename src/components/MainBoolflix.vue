<template>
  <main>
    <div v-if="arrMovies == null">Film in arrivo</div>
    <card-film
      v-else
      v-for="card in arrMovies"
      :key="card.title"
      :card="card"
    />
  </main>
</template>

<script>
/* eslint-disable */

import CardFilm from './CardFilm.vue'
import axios from 'axios'

export default {
  name: 'MainBoolflix',
  components: {
    CardFilm
  },
  data () {
    return {
      arrMovies: [],
    }
  },
  created () {
    /* using Giuseppe Mirizzi's api_key cause still unable to register */
    axios
    .get('https://api.themoviedb.org/3/search/movie?api_key=01af620fbe2924c05e6048caa6f5c225&language=it-IT&query=dune')
    .then((response) => {
      console.log(response);
      this.arrMovies = response.data.results;
    })
  }
}
</script>

<style scoped lang="scss">

</style>
