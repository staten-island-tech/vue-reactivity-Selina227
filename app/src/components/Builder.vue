<template>
  <div class="flex flex-col items-center justify-center min-h-screen bg-gray-100 p-6">
    <h2 class="head">Design Your Own Poke Bowl</h2>

    <div class="relative">
      <Bowl :ingredients="ingredients" />
    </div>

    <h3 class="section-title">Bases</h3>
    <div class="options">
      <div
        v-for="base in bases"
        :key="base.id"
        class="option-item"
        :class="{ selected: ingredients.base === base.name }"
        @click="toggleBase(base.name)"
      >
        <img :src="base.image" :alt="base.name" />
        <p>{{ base.name }}</p>
      </div>
    </div>

    <h3 class="section-title">Proteins</h3>
    <div class="options">
      <div
        v-for="protein in proteins"
        :key="protein.id"
        class="option-item"
        :class="{ selected: ingredients.protein === protein.name }"
        @click="toggleProtein(protein.name)"
      >
        <img :src="protein.image" :alt="protein.name" />
        <p>{{ protein.name }}</p>
      </div>
    </div>

    <h3 class="section-title">Toppings</h3>
    <div class="options">
      <div
        v-for="topping in toppings"
        :key="topping.id"
        class="option-item"
        :class="{ selected: selectedToppings.includes(topping.name) }"
        @click="toggleTopping(topping.name)"
      >
        <img :src="topping.image" :alt="topping.name" />
        <p>{{ topping.name }}</p>
      </div>

      <div class="w-full flex justify-center mt-4">
        <button @click="showOrder = true">View Order</button>
      </div>

      <Order v-if="showOrder" :ingredients="ingredients" />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import Bowl from './Bowl.vue'
import Order from './Order.vue'
const showOrder = ref(false)

const bases = ref([
  { id: 1, name: 'White Rice', image: '/white-rice.png' },
  { id: 2, name: 'Brown Rice', image: '/brown-rice.png' },
])

const proteins = ref([
  { id: 1, name: 'Salmon', image: '/salmon.png' },
  { id: 2, name: 'Chicken', image: '/chicken.png' },
  { id: 3, name: 'Steak', image: '/steak.png' },
])

const toppings = ref([
  { id: 1, name: 'Seaweed Salad', image: '/seaweed.png' },
  { id: 2, name: 'Crab Strips', image: '/crab-stick.png' },
  { id: 3, name: 'Wonton Crisps', image: '/wonton.png' },
  { id: 4, name: 'Cucumber', image: 'cucumber.png' },
  { id: 5, name: 'Scallion', image: '/scallion.png' },
  { id: 6, name: 'Sweet Corn', image: '/corn.png' },
])

const selectedBase = ref([])
const selectedProtein = ref([])
const selectedToppings = ref([])

const ingredients = {
  bases: selectedBase.value,
  proteins: selectedProtein.value,
  toppings: selectedToppings.value,
}

function toggleBase(base) {
  const index = selectedBase.value.indexOf(base)
  if (index === -1) {
    selectedBase.value.push(base)
  } else {
    selectedBase.value.splice(index, 1)
  }
}

function toggleProtein(protein) {
  const index = selectedProtein.value.indexOf(protein)
  if (index === -1) {
    selectedProtein.value.push(protein)
  } else {
    selectedProtein.value.splice(index, 1)
  }
}

function toggleTopping(topping) {
  const index = selectedToppings.value.indexOf(topping)
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
  text-align: center;
}

.section-title {
  font-size: 1.5rem;
  margin-top: 1rem;
}

.options {
  display: flex;
  justify-content: center;
  gap: 1rem;
  flex-wrap: wrap;
}

.option-item {
  text-align: center;
  border: 1px solid;
  padding: 0.5rem;
  background-color: pink;
  border-radius: 8px;
  border-color: salmon;
}

.option-item:hover {
  transition: transform 1s ease;
  transform: scale(1.1) translateY(-10px);
}

.option-item img {
  width: 80px;
  height: 80px;
}

.option-item.selected {
  border-color: #af4c4c;
  background-color: #f0fdf4;
}
</style>
