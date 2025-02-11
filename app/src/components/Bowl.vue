<template>
  <div class="bowl">
    <img src="/bowl-base.png" class="bowl-base" />

    <img
      v-if="ingredients.base"
      :src="`/${ingredients.base}.png`"
      :alt="topping.name"
      class="ingredient"
    />
    <img
      v-if="ingredients.protein"
      :src="`/${ingredients.protein}.png`"
      :alt="topping.name"
      class="ingredient"
    />
    <img
      v-for="topping in ingredients.toppings"
      :key="topping"
      :src="`/${topping}.png`"
      :alt="topping.name"
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

<style scoped></style>
