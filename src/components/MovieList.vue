<template>
<div>
  <Movie :movieData="movieData"/>
</div>
</template>

<script>
import Movie from "./Movie.vue";
import SearchBar from "./SearchBar.vue";

export default {
  name: 'MovieList',
  components: {
    Movie,
    SearchBar,
  },
  props:{
    movieData: Array,
  },
}

</script>

<style scoped>

</style>
