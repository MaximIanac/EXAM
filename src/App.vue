<template>
  <div id="app">
    <router-view @changeFact="handleChange"></router-view>
    <FooterComponent :fact="fact" />
  </div>
</template>

<script setup>
import axios from 'axios';
import { ref, onMounted } from 'vue';
import FooterComponent from './components/FooterComponent.vue';
const fact = ref('')

const handleChange = (value) => {
  fact.value = value;
  console.log(value);
}

onMounted(async () => {
  try {
    const response = await axios.get('https://uselessfacts.jsph.pl/api/v2/facts/random')
    fact.value = response.data.text;
  } catch (error) {
    console.error('Error fetching random fact:', error)
  }
})
</script>

