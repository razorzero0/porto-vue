<script setup>
import { DotLottieVue } from "@lottiefiles/dotlottie-vue";
</script>

<template>
  <div
    id="hero"
    class="relative flex flex-col items-center justify-center text-center min-h-[100vh] bg-gray-50 dark:bg-gray-900 hero px-6"
  >
    <!-- Teks -->
    <h1 class="text-5xl md:text-7xl mb-8 text-primary font-bold tracking-wider">
      Hi! I'm Ainun
    </h1>
    <p
      class="text-lg md:text-2xl text-gray-700 dark:text-gray-300 mb-8 max-w-5xl"
    >
      I am passionate about web development and love learning new technologies
      to create meaningful and functional digital experiences.
    </p>

    <!-- Gambar di bawah teks -->
    <img src="../assets/pp.png" class="w-64 rounded-full shadow-lg mt-8" />

    <DotLottieVue
      style="height: 100px; width: 100px; position: absolute; bottom: 30px"
      autoplay
      loop
      src="https://lottie.host/dbc6e249-fd68-4359-944b-b435e75d91e1/y2iEXbwqmO.lottie"
    />
  </div>
</template>

<style scoped>
.hero {
  @apply bg-[url('../assets/bg-light.svg')];
}

.dark .hero {
  @apply bg-[url('../assets/bg-dark.svg')];
}
</style>
