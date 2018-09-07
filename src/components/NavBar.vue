<template>
<nav class="navbar navbar-expand-lg navbar-light bg-light">
  <img alt="Vue logo" src="../assets/logo.png" style="width: 40px">
  <a class="navbar-brand" href="./main.js">Movies by Vue</a>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav mr-auto">
      <li class="nav-item active">
        <a class="nav-link" href="./main.js">Trending<span class="sr-only">(current)</span></a>
      </li>
      <li class="nav-item">
        <a class="nav-link" href="#"></a>
      </li>
    </ul>
    <form class="form-inline my-2 my-lg-0">
      <SearchBar v-on:addToSearchURL="searchEvent"/>
    </form>
  </div>
</nav>
</template>

<script>
import SearchBar from "./SearchBar.vue";

export default {
  name: 'NavBar',
    data: function() {
      return {
        searchTerm: "",
      };
    },
  components: {
    SearchBar,
  },
  methods:{
    searchEvent:function(searchTerm){
      console.log("Searched For", searchTerm)
      this.searchTerm = this.searchBar
      this.$emit('searchBar', searchTerm)
    }
  }
};
</script>

<style>
@media only screen and (max-width: 800px) {
  
}
</style>
