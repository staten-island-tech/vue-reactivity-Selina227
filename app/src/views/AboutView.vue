<template>
  <div class="container">
    <LogIn message="Hello" />
    <ToppingCard v-for="topping in toppings" :key="topping.name" />
  </div>
</template>

<script setup></script>

<style scoped></style>
