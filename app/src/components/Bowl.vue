<template>
  <div class="bowl">
    <img src="/bowl.png" class="bowl-base" />

    <img v-if="ingredients.base" :src="`/${ingredients.base}.png`" class="ingredient" />
    <img v-if="ingredients.protein" :src="`/${ingredients.protein}.png`" class="ingredient" />
    <img
      v-for="topping in ingredients.toppings"
      :key="topping"
      :src="`/${topping}.png`"
      class="ingredient"
    />
    <img
      v-for="extra in ingredients.extras"
      :key="extra"
      :src="`/${extra}.png`"
      class="ingredient"
    />
  </div>
</template>

<script setup>
defineProps({
  ingredients: Object,
})
</script>

<style scoped>
.bowl {
  position: relative;
  width: 300px;
  height: 300px;
}

.bowl-base {
  width: 100%;
  height: 100%;
}

.ingredient {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>
