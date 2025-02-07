<template>
  <div class="card">
    <h2>{{ topping.name }}</h2>
    <img :src="topping.image" alt="" />
    <button @click="add"></button>
  </div>
</template>

<script setup>
defineProps({
  topping: Array,
})
const topping = [
  { name: 'Seaweed Salad', price: '$3.00', image: '' },
  { name: 'Crab Strips', price: '$2.00', image: '' },
  { name: 'Wonton Crisps', price: '$1.50', image: '' },
  { name: 'Masago', price: '$3.00', image: '' },
  { name: 'Cucumber', price: '$1.00', image: '' },
  { name: 'Cherry Tomato', price: '$1.50', image: '' },
  { name: 'Scallion', price: '$1.00', image: '' },
  { name: 'Sweet Corn', price: '$1.00', image: '' },
]
</script>

<style scoped>
.card {
  background-color: aliceblue;
}
</style>
