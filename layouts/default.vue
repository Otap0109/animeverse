<template>
  <div>
    <header class="bg-gray-900 text-white shadow">
      <nav
        class="container mx-auto px-4 py-4 flex justify-between items-center"
      >
        <NuxtLink class="text-2xl font-bold tracking-wide" to="/">
          AnimeVerse
        </NuxtLink>
        <SearchBar />
      </nav>
    </header>

    <main class="container mx-auto px-4 py-6">
      <slot />
    </main>
  </div>
</template>
