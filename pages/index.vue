<script setup>
import { ref } from 'vue';
import axios from 'axios';

const data = ref([]);

try {
  const response = await axios.get('http://127.0.0.1:8000/api/anime/');
  data.value = response.data.results;
} catch (error) {
  console.error(error);
}
</script>

<template>
  <div>
    <AnimeCard :data="data" />
  </div>
</template>
