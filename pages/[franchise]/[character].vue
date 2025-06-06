<script setup>
import { useRoute } from "vue-router";
import { computed, ref } from "vue";

import axios from 'axios';

const route = useRoute();
const characterSlug = computed(() => route.params.character);

const character = ref(null);

try {
  const response = await axios.get(`http://127.0.0.1:8000/api/characters/`, {
    params: { 'slug': characterSlug.value }, // Filter by slug
  });
  character.value = response.data.results[0]; // Get the first character object
} catch (error) {
  console.error(error);
}
</script>

<template>
  <div
    v-if="character"
    class="flex flex-col md:flex-row gap-8 items-center justify-center p-6"
  >
    <CharDetail :character="character" :franchise="character.anime[0]" />
  </div>

  <div v-else>
    <NoPage />
  </div>
</template>
