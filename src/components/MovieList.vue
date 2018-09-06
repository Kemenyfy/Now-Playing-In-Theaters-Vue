<template>
<div>
  <header class="text-center m-4">Now Showing at your local Theater</header>
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
.text-center {
  font-weight: bold;
}
</style>
