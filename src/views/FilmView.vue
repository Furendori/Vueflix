<script setup>
import { onBeforeMount, ref } from 'vue'
import FooterView from '../components/FooterView.vue'
import { $fetch } from 'ohmyfetch';


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
    <div>
        <p class="movies-title" v-for="(movie, index) in movies" :key="index"> {{ movie.original_title }}</p>

    </div>
    <FooterView></FooterView>
</template>

<style>
    .movies-title {
        display: flex;
        flex-direction: column;
    }
</style>