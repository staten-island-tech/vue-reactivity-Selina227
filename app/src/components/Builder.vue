<template>
  <div class="bowl-builder">
    <h2>Title</h2>
    <div v-for="topping in toppings" :key="topping.id">
      <h3>{{ topping.name }}</h3>
      <p>{{ topping.price }}</p>
    </div>
  </div>
</template>

<script setup>
defineProps({
  toppings: Array,
})
const toppings = [
  { id: 1, name: 'Seaweed Salad', price: '$3.00', image: '' },
  { id: 2, name: 'Crab Strips', price: '$2.00', image: '' },
  { id: 3, name: 'Wonton Crisps', price: '$1.50', image: '' },
  { id: 4, name: 'Masago', price: '$3.00', image: '' },
  { id: 5, name: 'Cucumber', price: '$1.00', image: '' },
  { id: 6, name: 'Cherry Tomato', price: '$1.50', image: '' },
  { id: 7, name: 'Scallion', price: '$1.00', image: '' },
  { id: 8, name: 'Sweet Corn', price: '$1.00', image: '' },
]
</script>

<style scoped></style>
