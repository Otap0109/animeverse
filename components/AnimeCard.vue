<script setup>
defineProps({
    data: Object,
})
</script>

<template>
  <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 p-4">
    <div
      v-for="item in data"
      :key="item.id"
      class="bg-white rounded-2xl shadow-md transition duration-300 ease-in-out hover:-translate-y-1 hover:scale-105"
    >
       <NuxtLink :to="`/${item.slug}`" class="block"> 
        <img
          :src="item.image"
          :alt="item.title"
          class="w-full h-60 object-cover rounded-t-2xl"
        />
        <div class="p-4">
          <h2 class="text-2xl font-semibold text-gray-800">{{ item.title }}</h2>
          <p class="text-gray-600 text-sm mt-2 line-clamp-3">
            {{ item.description }}
          </p>
          <div class="mt-4 text-sm text-gray-500 space-y-1">
            <p>
              <span class="font-medium text-gray-700">Genre:</span>
              {{ item.genre }}
            </p>
            <p>
              <span class="font-medium text-gray-700">Release Year:</span>
              {{ item.release_date }}
            </p>
          </div>
        </div>
      </NuxtLink>
      
    </div>
  </div>
</template>