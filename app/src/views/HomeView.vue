<template>
  <div class="div">
    <h1>{{ count }}</h1>
    <button @click="increment">Click Me</button>
  </div>
</template>

<script setup>
import { ref } from 'vue'
let count = ref(0)
function increment() {
  count.value++
}
</script>

<style scoped></style>
