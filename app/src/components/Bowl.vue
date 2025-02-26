<template>
  <div class="bowl-container">
    <img src="/bowl.png" alt="Bowl" class="bowl-image" />

    <img
      v-for="(base, index) in ingredients.bases"
      :key="index"
      :src="getImagePath(base)"
      :alt="base"
      class="ingredient-layer base-layer"
    />

    <img
      v-for="(protein, index) in ingredients.proteins"
      :key="index"
      :src="getImagePath(protein)"
      :alt="protein"
      class="ingredient-layer protein-layer"
    />

    <img
      v-for="(topping, index) in ingredients.toppings"
      :key="index"
      :src="getImagePath(topping)"
      :alt="topping"
      class="topping-layer"
    />
  </div>
</template>

<script setup>
const props = defineProps({
  ingredients: Object,
})

const getImagePath = (ingredientName) => {
  const images = {
    'White Rice': '/white-rice.png',
    'Brown Rice': '/brown-rice.png',
    Salmon: '/salmon.png',
    Chicken: '/chicken.png',
    Steak: '/steak.png',
    'Seaweed Salad': '/seaweed.png',
    'Crab Strips': '/crab-stick.png',
    'Wonton Crisps': '/wonton.png',
    Cucumber: '/cucumber.png',
    Scallion: '/scallion.png',
    'Sweet Corn': '/corn.png',
  }
  return images[ingredientName] || ''
}
</script>

<style scoped>
.bowl-container {
  position: relative;
  width: 300px;
  height: 300px;
}

.bowl-image {
  width: 100%;
  height: auto;
}

.ingredient-layer {
  position: absolute;
  width: 200px;
  height: 200px;
}

.base-layer {
  top: 50px;
  left: 50px;
}

.protein-layer {
  top: 40px;
  left: 60px;
}

.topping-layer {
  position: absolute;
  width: 200px;
  height: 200px;
  top: 40px;
  left: 60px;
}
</style>
