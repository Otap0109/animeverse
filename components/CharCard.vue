<template>
    <div class="p-4 sm:p-6 grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
      <NuxtLink
        v-for="char in characters"
        :key="char.id"
        :to="`/${franchise}/${char.slug}`"
        class="block bg-white rounded-2xl shadow-md transition duration-300 ease-in-out hover:-translate-y-1 hover:scale-105"
      >
        <img
          :src="char.image"
          :alt="char.name"
          class="w-full h-60 object-cover rounded-t-2xl"
        />
        <div class="p-4">
          <h2 class="text-xl font-semibold text-gray-800">{{ char.name }}</h2>
          <p class="text-gray-600 text-sm mt-1 line-clamp-3">
            {{ char.description }}
          </p>
          <div class="text-gray-500 text-sm mt-2">
            <span class="font-medium">Age:</span> {{ char.age }}<br />
            <span class="font-medium">Role:</span> {{ char.role }}
          </div>
        </div>
      </NuxtLink>
    </div>
  </template>
  
  <script setup>
  defineProps({
    characters: Array,
    franchise: String
  });
  </script>
  