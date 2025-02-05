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
const topping = [
  { name: 'Seaweed Salad', image: '' },
  { name: 'Crab Strips', image: '' },
  { name: 'Wonton Crisps', image: '' },
  { name: 'Masago', image: '' },
  { name: 'Cucumber', image: '' },
  { name: 'Cherry Tomato', image: '' },
  { name: 'Scallion', image: '' },
  { name: 'Sweet Corn', image: '' },
]
</script>

<style scoped>
.card {
  background-color: aliceblue;
}
</style>
