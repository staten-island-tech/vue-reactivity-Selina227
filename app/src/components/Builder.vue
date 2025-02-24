<template>
  <div class="bowl-builder">
    <h2 class="head">Design Your Own Poke Bowl</h2>

    <Bowl :ingredients="ingredients" />
    <Order :ingredients="ingredients" />

    <h3 class="section-title">Base</h3>
    <div class="options">
      <div
        v-for="base in bases"
        :key="base.id"
        class="option-item"
        :class="{ selected: ingredients.base === base.name }"
        @click="selectBase(base.name)"
      >
        <img :src="base.image" :alt="base.name" />
        <p>{{ base.name }}</p>
      </div>
    </div>

    <h3 class="section-title">Protein</h3>
    <div class="options">
      <div
        v-for="protein in proteins"
        :key="protein.id"
        class="option-item"
        :class="{ selected: ingredients.protein === protein.name }"
        @click="selectProtein(protein.name)"
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
      <button @click="showOrder = true">View Order</button>
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
])

const toppings = ref([
  { id: 1, name: 'Seaweed Salad', price: '$3.00', image: '/seaweed.png' },
  { id: 2, name: 'Crab Strips', price: '$2.00', image: '/crab-stick.png' },
  { id: 3, name: 'Wonton Crisps', price: '$1.50', image: '/wonton.png' },
  { id: 4, name: 'Cucumber', price: '$1.00', image: 'cucumber.png' },
  { id: 5, name: 'Scallion', price: '$1.00', image: '/scallion.png' },
  { id: 6, name: 'Sweet Corn', price: '$1.00', image: '/corn.png' },
])

const selectedBase = ref([])
const selectedProtein = ref([])
const selectedToppings = ref([])

const ingredients = {
  base: selectedBase.value,
  protein: selectedProtein.value,
  toppings: selectedToppings.value,
}

function selectBase(base) {
  selectedBase.value = base
}

function selectProtein(protein) {
  selectedProtein.value = protein
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
  justify-content: center;
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
  cursor: pointer;
  text-align: center;
  border: 1px solid transparent;
  padding: 0.5rem;
  transition: 0.3s;
}

.option-item img {
  width: 80px;
  height: 80px;
}

.option-item.selected {
  border-color: #4caf50;
  background-color: #f0fdf4;
}
</style>
