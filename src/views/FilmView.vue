<script setup>
import { onBeforeMount, ref } from 'vue'
import FooterView from '../components/FooterView.vue'
import { $fetch } from 'ohmyfetch'
import MovieCard from '../components/MovieCard.vue'

const api = $fetch.create({ baseURL: 'https://api.vueflix.boxydev.com/movies' })
const getMovies = async () => {
  return api('/api/movies', { method: 'GET' })
}

let movies = ref([])

onBeforeMount(() => {
  getMovies().then((response) => (movies.value = response))
})
</script>

<template>
  <h1 class="films">Films</h1>
  <div class="content">
    <div class="movie-item"  >
      <!-- <div class="movie-image">
        <img :src="movie.poster_path" :alt="movie.title" />
      </div>
      <div class="movie-infos">
        <p class="movie-title">{{ movie.title }}</p>
        <p class="movie-date">{{ movie.release_date }}</p>
      </div> -->
      <MovieCard v-for="movie in movies" :key="movie.id" :movie="movie"/>
    </div>
  </div>

  <FooterView />
</template>

<style>
body {
  background-color: rgb(229, 231, 235);
}

.films {
  text-align: center;
  font-size: 70px;
}

.content {
  flex-wrap: wrap;
  margin-left: 5%;
  display: flex;
  flex-direction: row;
}

.movie-item {
  display: flex;
  flex-wrap: wrap;
  margin: 20px;
  width: auto;
}

img {
  height: 400px;
  border-radius: 10px 10px 0 0;
}

</style>