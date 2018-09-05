<template>
  <MovieList  :movieData="movieData"/>
</template>

<script>
import MovieList from "./components/MovieList.vue";

export default {
  name: "app",
  components: {
    MovieList
  },
  data:function(){
    return {
      movieData:[]
    }
  },
  mounted: function() {
    const Url = "https://api.themoviedb.org/3/search/movie?api_key=9fe2614f2b9d0f56b7e758ac2b8ef828&query=meg&language=en-US&page=1&include_adult=false"
    fetch(Url)
      .then(resp => resp.json())
      .then(data => {
        console.log(data)
        this.movieData = data.results
      });
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
