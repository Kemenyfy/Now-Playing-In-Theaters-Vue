<template>
<div>
  <NavBar v-on:searchBar="Search" />
  <MovieList :movieData="movieData" />
</div>
</template>

<script>
import NavBar from "./components/NavBar.vue";
import MovieList from "./components/MovieList.vue";
import SearchBar from "./components/SearchBar.vue";

export default {
  name: "app",
  components: {
    NavBar,
    MovieList,
    SearchBar
  },
  data: function() {
    return {
      movieData: [],
      addToUrl:""
    };
  },
  mounted: function() {
    this.updateComponent();
  },
  methods: {
    Search: function(addToUrl) {
      console.log("Caught Emit", addToUrl);
      this.addToUrl = addToUrl
      this.updateComponent();
    },
    updateComponent: function() {
      if (this.addToUrl) {
        let searchURL = `https://api.themoviedb.org/3/search/movie?api_key=9fe2614f2b9d0f56b7e758ac2b8ef828&query=${
          this.addToUrl
        }&language=en-US&page=1&include_adult=false`;
        fetch(searchURL)
          .then(resp => resp.json())
          .then(data => {
            console.log(data.results);
            this.movieData = data.results;
          });
      } else {
        const Url =
          "https://api.themoviedb.org/3/movie/popular?api_key=9fe2614f2b9d0f56b7e758ac2b8ef828&query=meg&language=en-US&page=1&include_adult=false";
        fetch(Url)
          .then(resp => resp.json())
          .then(data => {
            this.movieData = data.results;
          });
      }
    }
  }
};
</script>

<style>
#app {
  font-family: 'Abhaya Libre', serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
