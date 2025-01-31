<template>
  <div>
    <h2>{{ topping.name }}</h2>
    <img :src="topping.image" alt="" />
  </div>
</template>

<script setup>
defineProps({
  topping: Object,
})
</script>

<style scoped></style>
