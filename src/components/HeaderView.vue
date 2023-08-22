<script setup>
import { ref } from 'vue'
/* import HomeView from '../views/HomeView.vue' */

let name = ref('Anthony')
let userConnected = ref(false)
let toggle = () => {
  userConnected.value = !userConnected.value
}
</script>

<template>
  <header>
    <div class="container">
      <h1>Vue<span class="flix">Flix</span></h1>
      <div class="navigation">
        <nav class="nav-bar">
          <router-link to="/"> Accueil </router-link>
          <router-link to="/about"> A Propos </router-link>
          <router-link to="/films"> Films </router-link>
        </nav>
        <div v-if="!userConnected">
          <button @click="toggle">Connexion</button>
        </div>
        <div v-else class="user-logged">
          <p>{{ name }}</p>
          <img
            src="https://www.google.com/url?sa=i&url=https%3A%2F%2Funsplash.com%2Fs%2Fphotos%2Fuser-profile&psig=AOvVaw2zX3ezX_FArXhi70tedCTa&ust=1692696243276000&source=images&cd=vfe&opi=89978449&ved=0CBAQjRxqFwoTCLCMlIS37YADFQAAAAAdAAAAABAE"
            alt="photo profil"
          />
          <button @click="toggle">X</button>
        </div>
      </div>
    </div>
  </header>
</template>

<style>
/* template {
  height: 100%;
  width: 100%;
  margin: 0;
  padding: 0;
} */

.container {
  position: relative;
  width: 100%;
  min-width: 1100px;
  height: 50px;
}

.container {
  display: flex;
  flex-direction: row;
}

a {
  color: white;
  text-decoration: none;
}

.user-logged {
  color: white;
}

.homeview-app {
  margin: 0;
}

.navigation {
  display: flex;
}

h1 {
  margin: 0;
}

.flix {
  color: darksalmon;
}
</style>
