<script setup>
defineProps(['movie'])
import dayjs from 'dayjs'
import 'dayjs/locale/fr'

dayjs.locale('fr')
</script>

<template>
  <div class="card">
    <div class="content">
      <div class="image-container">
        <RouterLink :to="`/films/`">
          <img :src="movie.poster_path" :alt="movie.title" class="movie-img"/>
        </RouterLink>
        <div class="card-content">
          <h2>
            <RouterLink class="movie-title" :to="`/films/`">{{ movie.title }}</RouterLink>
          </h2>
          <p class="movie-date">{{ dayjs(movie.release_date).format('DD MMMM YYYY') }}</p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.card {
  margin-bottom: 20px;
  width: 300px;
}
.movie-img{
  width: 100%;
}
.content {
  background-color: #fff;
  border-radius: 10px;
  box-shadow: 0 1px 3px 0 #0000001a;
  margin: 0 10px;
  display: flex;
  flex-direction: column;
  height: 100%;
}

.image-container {
  position: relative;
}

.note-container {
  position: absolute;
  bottom: 10px;
  left: 10px;
  background-color: #000;
  width: 48px;
  height: 48px;
  border-radius: 50%;
  border: 2px solid #000;
}

.green {
  border-color: #22c55e;
}

.yellow {
  border-color: #eab308;
}

.red {
  border-color: #ef4444;
}

span {
  color: #fff;
  font-weight: 700;
  display: flex;
  align-items: center;
  height: 100%;
  justify-content: center;
}

img {
  height: 400px;
  width: fit-content;
  object-fit: cover;
  border-radius: 10px 10px 0 0;
  display: block;
}

.card-content {
  padding: 12px;
  display: flex;
  flex-direction: column;
  height: 100%;
}

h2 {
  font-size: 16px;
  display: flex;
  flex-wrap: wrap;
}

a {
  color: #000;
}

.movie-date {
  color: #9ca3af;
}

.movie-title {
  display: flex;
}
</style>
