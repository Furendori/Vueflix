<script setup>
import { computed } from 'vue'
const props = defineProps(['note'])

const percentage = computed(() => Math.ceil(props.note * 10))
</script>

<template>
  <div
    class="movie-note"
    :class="{
      green: percentage >= 70,
      yellow: percentage >= 49 && percentage <= 69,
      red: percentage <= 48
    }"
  >
    <span>{{ percentage }}%</span>
  </div>
</template>

<style>
.note-container {
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
</style>
