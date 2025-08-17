<template>
  <footer
    class="relative bg-gray-100 dark:bg-gray-900 text-gray-700 dark:text-gray-300 py-6 px-8 mt-10"
  >
    <div
      class="max-w-7xl mx-auto flex flex-col md:flex-row items-center justify-between gap-4"
    >
      <!-- Left -->
      <p class="text-sm">
        &copy; {{ new Date().getFullYear() }} Ainun. All rights reserved.
      </p>

      <!-- Right -->
      <div class="flex space-x-4">
        <a
          href="https://www.instagram.com/m_ainunnn/"
          target="_blank"
          class="w-10 h-10 flex items-center justify-center rounded-full bg-gray-200 dark:bg-gray-800 hover:bg-primary hover:text-white transition-colors duration-300"
        >
          <i class="fab fa-instagram text-lg"></i>
        </a>
        <a
          href="https://t.me/+6285731013100"
          target="_blank"
          class="w-10 h-10 flex items-center justify-center rounded-full bg-gray-200 dark:bg-gray-800 hover:bg-primary hover:text-white transition-colors duration-300"
        >
          <i class="fab fa-telegram text-lg"></i>
        </a>
        <a
          href="https://github.com/razorzero0"
          target="_blank"
          class="w-10 h-10 flex items-center justify-center rounded-full bg-gray-200 dark:bg-gray-800 hover:bg-primary hover:text-white transition-colors duration-300"
        >
          <i class="fab fa-github text-lg"></i>
        </a>
        <a
          href="https://www.linkedin.com/in/muhammad-ainun-yanuar"
          target="_blank"
          class="w-10 h-10 flex items-center justify-center rounded-full bg-gray-200 dark:bg-gray-800 hover:bg-primary hover:text-white transition-colors duration-300"
        >
          <i class="fab fa-linkedin text-lg"></i>
        </a>
      </div>
    </div>

    <!-- Arrow to top -->
    <button
      @click="scrollToTop"
      class="absolute -top-5 left-1/2 -translate-x-1/2 w-16 h-16 flex items-center justify-center rounded-full bg-gray-100 dark:bg-gray-800 hover:bg-primary hover:text-white hover:-translate-y-2 transition-all duration-300 cursor-pointer"
    >
      <i class="fas fa-caret-up text-3xl"></i>
    </button>
  </footer>
</template>

<script setup>
const scrollToTop = () => {
  window.scrollTo({ top: 0, behavior: "smooth" });
};
</script>

<style>
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css");
</style>
