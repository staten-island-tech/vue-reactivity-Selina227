<template>
  <div id="app">
    <Builder :toppings="toppings" />
  </div>
</template>

<script setup>
import Builder from './components/Builder.vue'
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

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
