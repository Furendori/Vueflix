<script setup>
import { onBeforeMount, ref } from 'vue';
import { $fetch } from 'ohmyfetch';
let date = new Date().getFullYear()

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
  <footer>
    <div>
      <p>Copyright © {{ date }}. Catalogue de {{ movies.length }} films</p>
    </div>
  </footer>
</template>

<style>
  footer {
    margin: 0;
  }
</style>