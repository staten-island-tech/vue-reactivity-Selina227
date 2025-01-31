<template>
  <div class="container">
    <LogIn message="Hello" />
    <AnimalCard v-for="animal in animals" :key="animal.name" />
  </div>
</template>

<script setup>
import NewList from '../components/NewList.vue'
import { reactive } from 'vue'
const user = reactive({ username: '', password: '' })
function login(user) {
  console.log(user)
}
</script>

<style scoped></style>
