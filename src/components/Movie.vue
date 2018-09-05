<template>
    <section class="row p-4">
        <div class="col-md-4 text-center card" v-for="movie in movieData" v-bind:key="movie.id">
            <p class="card-title">{{ movie.title }}</p>
            <img :src="getImageUrl(movie.poster_path)" class="img-thumbnail p-2" alt=""/>
            <p>Released Date: {{ movie.release_date }}</p>
        </div>
    </section>
</template>

<script>
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
}
</script>

<style>
.img-thumbnail {
    max-height: 600px;
}
</style>

