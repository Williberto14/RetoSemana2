<template>
    <div id="peliculas">
    <div class="row mt-md-5 mt-sm-5 mt-xs-5">
        <div class="col-lg-6 col-xs-12" v-for="(movie, index) of movies" :key="index">
          <div class="d-flex justify-content-center align-items-center">
            <div class="p-3">
              <img :src="movie.Poster" alt="Movie poster">
            </div>
            <div class="p-2">
                <h3>{{ movie.Title }}</h3>
                <hr>
              <h4>Año: {{movie.Year}}</h4>
            </div>

          </div>
          <div class="d-flex container-fluid justify-content-end pb-2 mt-n2">
            <a :href="'https://imdb.com/title/' + movie.imdbID" target="_blank" class="btn btn-outline-info">Info</a>
          </div>
    </div>
    </div>
    </div>

</template>


<script>

const axios = require('axios');

export default {
    name: 'ApiPeliculas',
    data(){
        return{
            movies: null
        }
    },
    mounted(){
        axios
        .get('http://www.omdbapi.com/?s=Avengers&type=movie&apikey=5d668009')
        .then(response => {
            (this.movies = response.data.Search.slice(0,4))
        })
    }
}
</script>

<style scoped>

</style>