<template>
  <div class="bowl-builder">
    <h2>Design Your Own Poke Bowl</h2>

    <div class="bowl-container">
      <img src="/bowl.png" alt="Base Bowl" class="bowl" />
      <img
        v-for="topping in selectedToppings"
        :key="topping.id"
        :src="topping.image"
        :alt="topping.name"
        class="topping"
      />
    </div>

    <div class="toppings-list">
      <div
        v-for="topping in toppings"
        :key="topping.id"
        class="topping-item"
        @click="placeTopping(topping)"
      >
        <img :src="topping.image" :alt="topping.name" class="topping-icon" />
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

const selectedToppings = ref([])

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
.bowl-builder {
  display: flex;
  flex-direction: column;
  align-items: center;
  row-gap: 30px;
}

.bowl-container {
  width: 300px;
  height: 300px;
}

.bowl {
  width: 100%;
}

.topping {
  position: absolute;
  width: 100px;
  top: 50px;
  left: 50px;
}

.toppings-list {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-top: 20px;
}

.topping-item {
  text-align: center;
}

.topping-icon {
  width: 50px;
  height: 50px;
}
</style>
