<template>
  <form v-on:submit.prevent="enterSearch">
    <input class="form-control mr-sm-2" placeholder="Search" v-model="searchBarInput" >
    <button class="btn btn-outline-success my-2 my-sm-0" >Search</button>
  </form>
</template>

<script>
export default {
    name: 'SearchBar',
      data: function() {
        return {
          searchBar: "",
          searchBarInput: ""
        };
      },
    methods: {
      enterSearch: function() {
        this.searchBar = this.searchBarInput
        this.$emit('addToSearchURL', this.searchBar)
      }
    }
}
</script>

<style>

</style>
