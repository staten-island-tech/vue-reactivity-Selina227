<template>
  <div class="bowl-builder">
    <h2>Title</h2>
    <div v-for="(topping, index) in toppings" :key="index"></div>
    <h3>{{ topping.name }}</h3>
  </div>
</template>

<script setup>
defineProps({
  toppings: Array,
})
const toppings = [
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

<style scoped></style>
