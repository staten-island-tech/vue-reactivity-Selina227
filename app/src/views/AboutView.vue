<template>
  <div class="container">
    <LogIn message="Hello" />
    <ToppingCard v-for="topping in toppings" :key="topping.name" />
  </div>
</template>

<script setup>
import ToppingCard from '../components/ToppingCard.vue'
const toppings = [
  { name: 'Seaweed Salad', image: '' },
  { name: 'Crab Strips', image: '' },
  { name: 'Wonton Crisps', image: '' },
  { name: 'Masago', image: '' },
  { name: 'Cucumber', image: '' },
  { name: 'Cherry Tomato', image: '' },
]
</script>

<style scoped></style>
