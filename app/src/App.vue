<template>
  <div id="app">
    <Builder />
  </div>
</template>

<script setup>
import Builder from './components/Builder.vue'
</script>

<style scoped>
@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }
}
</style>
