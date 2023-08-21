<script setup>
import { ref } from 'vue'

let userConnected = ref(false)
let name = ref('Anthony')
</script>

<template>
  <header>
    <nav>
      <a href="#">Accueil</a>
      <a href="#">A propos</a>
    </nav>
    <div v-if="userConnected = false">
        <button @click="userConnected = true">Connexion</button>
    </div>
    <div>
        <p>{{ name }}</p>
        <img src="https://www.google.com/url?sa=i&url=https%3A%2F%2Funsplash.com%2Fs%2Fphotos%2Fuser-profile&psig=AOvVaw2zX3ezX_FArXhi70tedCTa&ust=1692696243276000&source=images&cd=vfe&opi=89978449&ved=0CBAQjRxqFwoTCLCMlIS37YADFQAAAAAdAAAAABAE" alt="photo profil">
    </div>
  </header>
</template>
