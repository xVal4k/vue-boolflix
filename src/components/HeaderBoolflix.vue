<template>
  <header>
    <h1 class="logo">BOOLFLIX</h1>
    <div class="header-right">
      <label for="movie-search">
        <input type="text" name="movie-search" id="movie-search" placeholder="Digita il titolo">
      </label>
      <button>Cerca</button>
    </div>
  </header>
</template>

<script>
/* eslint-disable */
export default {
  name: 'HeaderBoolflix',
  data () {
    return {
    }
  }
};
</script>

<style scoped lang="scss">
  h1 {
    color: red;
  }

  input,
  button {
    height: 2rem;
    border-radius: 5px;
    border: solid 1px transparent;
  }

  input {
    padding: 0 .5rem;
  }

  button {
    padding: 0 1.5rem;
    background: red;
    color: white;
    cursor: pointer;
  }
</style>
