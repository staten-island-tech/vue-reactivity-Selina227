<template>
  <div class="order-summary">
    <h2>Your Poke Bowl Order</h2>

    <div class="order-details">
      <p><strong>Base:</strong> {{ ingredients.bases || 'None selected' }}</p>
      <p><strong>Protein:</strong> {{ ingredients.proteins || 'None selected' }}</p>

      <p><strong>Toppings:</strong></p>
      <ul>
        <li v-if="ingredients.toppings.length === 0">None selected</li>
        <li v-for="topping in ingredients.toppings" :key="topping">{{ topping }}</li>
      </ul>
    </div>

    <button @click="placeOrder">Confirm Order</button>
  </div>
</template>

<script setup>
const props = defineProps({
  ingredients: Object,
})

const placeOrder = () => {
  alert(
    `Your order has been placed! 🎉\n\nBase: ${props.ingredients.bases || 'None'}\nProtein: ${props.ingredients.proteins || 'None'}\nToppings: ${props.ingredients.toppings || 'None'}`,
  )
}
</script>

<style scoped>
.order-summary {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  padding: 2rem;
  border: 2px solid salmon;
  border-radius: 10px;
  background-color: pink;
  width: 400px;
  margin: auto;
}

.order-details {
  margin-top: 1rem;
}

ul {
  list-style-type: none;
  padding: 0;
}

button {
  margin-top: 1rem;
  padding: 0.5rem 1rem;
  border: none;
  background-color: #4caf50;
  color: white;
  cursor: pointer;
  border-radius: 5px;
  font-size: 1rem;
}

button:hover {
  background-color: #45a049;
}
</style>
