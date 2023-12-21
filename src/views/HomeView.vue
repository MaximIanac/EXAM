<template>
  <div class="home">
    <h1>Hello, Facto!</h1>
    <router-link @changeFact="setFact" @click="setFact" to="/fact">Random Fact</router-link>
  </div>
</template>

<script setup>
const emit = defineEmits(['changeFact']);

const setFact = (value) => {
  emit('changeFact', value);
}
</script>

<style>
.home {
  text-align: center;
  margin-top: 50px;
}
</style>
