<template>
  <div class="fact-detail">
    <h1>Random Fact Details</h1>
    <p>{{ fact }}</p>
    <button @click="$router.go(-1)">Back</button>
  </div>
</template>

<script setup>
import axios from 'axios';
import { onMounted } from 'vue';
import { ref } from 'vue';

const fact = ref('');
const emit = defineEmits(['changeFact']);

onMounted(async () => {
  try {
    const response = await axios.get('https://uselessfacts.jsph.pl/api/v2/facts/random')
    fact.value = response.data.text;
    emit('changeFact', response.data.text);
  } catch (error) {
    console.error('Error fetching random fact:', error)
  }
})

</script>

<style>
.fact-detail {
  margin: 20px;
}
</style>
