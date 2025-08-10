<script setup>
import { DotLottieVue } from "@lottiefiles/dotlottie-vue";
</script>

<template>
  <div
    id="hero"
    class="relative flex flex-col items-center justify-center text-center min-h-[100vh] bg-gray-50 dark:bg-gray-900 hero px-6"
  >
    <!-- Teks -->
    <h1
      class="text-4xl md:text-6xl mb-4 md:mb-8 text-primary font-bold tracking-wider uppercase"
    >
      Hey, I'm Ainun
    </h1>
    <p
      class="text-md md:text-xl text-gray-700 dark:text-gray-300 mb-8 md:mb-12 max-w-5xl"
    >
      I am passionate about web development and love learning new technologies
      to create meaningful and functional digital experiences.
    </p>

    <!-- Gambar di bawah teks -->
    <img src="../assets/pp.png" class="w-48 md:w-60 rounded-full shadow-lg" />

    <DotLottieVue
      style="height: 80px; width: 80px; position: absolute; bottom: 20px"
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
