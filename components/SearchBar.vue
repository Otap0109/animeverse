<template>
    <div class="w-full max-w-md mx-auto">
      <div class="relative">
        <input
          v-model="query"
          type="text"
          placeholder="Search..."
          class="w-full pl-12 pr-4 py-3 rounded-2xl shadow-md border border-gray-200 focus:outline-none focus:ring-1 transition-all"
        />
        <div class="absolute left-4 top-1/2 transform -translate-y-1/2 text-gray-400">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            class="h-5 w-5"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M21 21l-4.35-4.35m0 0A7.5 7.5 0 103.5 3.5a7.5 7.5 0 0013.15 13.15z"
            />
          </svg>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue'
  
  const query = ref('')
  </script>
  