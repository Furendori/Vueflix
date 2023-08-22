<script setup>
/* import { $fetch } from 'ohmyfetch'; */
import HeaderView from '../src/components/HeaderView.vue'
</script>

<template>
  <div class="app-header">
    <HeaderView></HeaderView>
  </div>

  <RouterView />
</template>


<style>
  .app-header {
    background-color: rgb(58, 64, 80);
  }

  body {
    margin: 0;
  }
</style>