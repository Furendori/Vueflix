<script setup>
import { ref } from 'vue';
import avatar1 from '../images/remix-7b59a15f-3878-4341-bad7-515f9490f204.png'
import avatar2 from '../images/profile_user.jpg'
import avatar3 from '../images/photo-1535713875002-d1d0cf377fde.jpeg'
let cards = ref({
  names : ["Jean-Pierre", "Jocelin", "Annette"],
  roles : ["Manager", "Développeur", "Commercial"],
  photo : [avatar1, avatar2, avatar3]
})
</script>

<template>
  <div class="about">
    <h1>A Propos</h1>
    <p class="names-about" v-for="(name, index) in cards.names" :key="index">{{ name }}</p>

  </div>
</template>