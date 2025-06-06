<script setup>
import { ref, computed } from 'vue';
import { useRoute } from 'vue-router';
import axios from 'axios';

const route = useRoute();
const franchise = computed(() => route.params.franchise);

const characters = ref([]);

try {
  const response = await axios.get(`http://127.0.0.1:8000/api/character/`, {
    params: { 'anime__slug': franchise.value }, // Filter by anime slug
  });
  characters.value = response.data.results;
} catch (error) {
  console.error(error);
}
</script>

<template>
  <div v-if="characters.length">
    <CharCard :franchise="franchise" :characters="characters" />
  </div>
  <div v-else>
    <NoPage />
  </div>
</template>
