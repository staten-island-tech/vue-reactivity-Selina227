<template>
  <div class="card">
    <h2>{{ topping.name }}</h2>
    <img :src="topping.image" alt="" />
    <button @click="add"></button>
  </div>
</template>

<script setup>
defineProps({
  topping: Object,
})
</script>

<style scoped></style>
