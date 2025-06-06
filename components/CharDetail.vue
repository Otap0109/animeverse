<script setup>
defineProps({
  character: {
    type: Object,
    required: true,
  },
  franchise: {
    type: Object,
    required: false,
  },
});
</script>

<template>
  <div v-if="character" class="flex flex-col md:flex-row gap-8 items-center justify-center p-6">
    <div class="w-full md:w-1/2 max-w-md">
      <img
        :src="character.image"
        :alt="character.name"
        class="w-full h-auto object-cover rounded-2xl shadow-md"
      />
    </div>
    <div class="w-full md:w-1/2 max-w-xl bg-white p-6 rounded-2xl shadow-md">
      <h1 class="text-4xl font-bold text-gray-800 mb-4">{{ character.name }}</h1>
      <p class="text-gray-600 text-lg leading-relaxed mb-4">{{ character.description }}</p>
      <div class="text-gray-700 space-y-2 font-semibold">
        <p><span>Role:</span> {{ character.role || 'Unknown' }}</p>
        <p><span>Age:</span> {{ character.age || 'Unknown' }}</p>
        <p><span>Anime:</span> {{ franchise?.title || 'Unknown' }}</p>
      </div>
    </div>
  </div>
</template>
