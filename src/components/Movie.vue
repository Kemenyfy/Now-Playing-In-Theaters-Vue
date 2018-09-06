<template>
<section class="row p-4 m-0">
  <div class="card" v-for="movie in movieData" v-bind:key="movie.id">
    <img class="card-img-top" :src="getImageUrl(movie.poster_path)" alt="Card image cap">
    <div class="card-body">
      <!-- <h4 class="card-title">{{ movie.title }}</h4> -->
      <p class="card-text">Released Date: {{ movie.release_date }}</p>
      <a href="#!" class="btn btn-primary">Movie Details</a>
    </div>
  </div>
</section>
</template>

<script>
import SearchBar from "./SearchBar.vue";

export default {
  name: "Movie",
  props: {
    movieData: Array
  },
  methods: {
    getImageUrl(poster_path) {
      return "https://image.tmdb.org/t/p/w500" + poster_path;
    }
  }
};
</script>

<style scoped>
.card {
    margin: 1em;
    border-radius: 1em;
    max-width: 18em;
}

.row {
    justify-content: space-around;
}
</style>

