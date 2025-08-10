<script setup>
import Navbar from "./components/Navbar.vue";
</script>

<template>
  <div
    class="relative min-h-screen bg-gray-50 dark:bg-gray-900 text-gray-800 dark:text-gray-100 overflow-hidden"
  >
    <div class="relative">
      <Navbar />
      <main>
        <RouterView />
      </main>
    </div>
  </div>
</template>

<style scoped></style>
