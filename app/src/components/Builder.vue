<template>
  <div class="bowl-builder">
    <h2 class="head">Design Your Own Poke Bowl</h2>

    <div>
      <img src="/bowl.png" alt="bowl" class="bowl" />
      <img
        v-for="topping in selectedToppings"
        :key="topping.id"
        :src="topping.image"
        :alt="topping.name"
        class="topping"
      />
    </div>
    <h3 class="head">Toppings</h3>
    <div class="max-w-sm rounded overflow-hidden shadow-lg w-full flex items-center">
      <div
        v-for="topping in toppings"
        :key="topping.id"
        class="topping-item"
        @click="placeTopping(topping)"
      >
        <img :src="topping.image" :alt="topping.name" class="topping-img" />
        <h3>{{ topping.name }}</h3>
        <p>{{ topping.price }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const toppings = ref([
  { id: 1, name: 'Seaweed Salad', price: '$3.00', image: 'seaweed.png' },
  { id: 2, name: 'Crab Strips', price: '$2.00', image: '/toppings/crab.png' },
  { id: 3, name: 'Wonton Crisps', price: '$1.50', image: '/wonton.png' },
  { id: 4, name: 'Masago', price: '$3.00', image: '/masago.png' },
  { id: 5, name: 'Cucumber', price: '$1.00', image: 'cucumber.png' },
  { id: 6, name: 'Cherry Tomato', price: '$1.50', image: '/tomato.png' },
  { id: 7, name: 'Scallion', price: '$1.00', image: '/scallion.png' },
  { id: 8, name: 'Sweet Corn', price: '$1.00', image: '/corn.png' },
])

const selectedToppings = ref([toppings])

function placeTopping(topping) {
  const index = selectedToppings.value.findIndex((t) => t.id === topping.id)
  if (index === -1) {
    selectedToppings.value.push(topping)
  } else {
    selectedToppings.value.splice(index, 1)
  }
}
</script>

<style scoped>
@import 'tailwindcss';
*,
body,
html {
  padding: 0%;
  margin: 0%;
  box-sizing: border-box;
  align-items: center;
  font-size: 10px;
}

.bowl-builder {
  display: flex;
  flex-direction: column;
  align-items: center;
  row-gap: 2rem;
}

.head {
  text-align: center;
  font-size: 2rem;
}

.bowl {
  width: 30rem;
  height: 30rem;
}

.topping {
  position: absolute;
  width: 25rem;
  height: 25rem;
  right: 47rem;
  top: 7rem;
}

.toppings-list {
  display: flex;
  flex-wrap: wrap;
  gap: 1rem;
  margin-top: 2rem;
}

.topping-item {
  text-align: center;
}

.topping-img {
  width: 130px;
  height: 100px;
}
</style>
