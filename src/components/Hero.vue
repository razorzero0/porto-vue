<script setup>
import { ref, onMounted, onUnmounted } from "vue";
import { DotLottieVue } from "@lottiefiles/dotlottie-vue";

const showAnim = ref(false);

const scrollToSection = (id) => {
  const el = document.getElementById(id);
  if (el) {
    el.scrollIntoView({ behavior: "smooth" });
  }
};

const parallaxY = ref(0);

const handleScroll = () => {
  // semakin di-scroll, semakin geser background
  parallaxY.value = window.scrollY * 0.4; // ubah multiplier sesuai selera
};

onMounted(() => {
  showAnim.value = true;
  window.addEventListener("scroll", handleScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>

<template>
  <div
    id="hero"
    class="relative flex flex-col items-center justify-center text-center min-h-[100vh] bg-gray-50 dark:bg-gray-900 hero px-6 bg-[url(../assets/bg-light.svg)] bg-fixed"
    :style="{ backgroundPositionY: `-${parallaxY}px` }"
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

    <Transition name="bounce">
      <!-- Gambar di bawah teks -->
      <img
        v-if="showAnim"
        src="@/assets/ppc.png"
        class="w-48 md:w-60 rounded-full shadow-lg"
      />
    </Transition>
    <DotLottieVue
      @click="scrollToSection('about')"
      style="
        height: 80px;
        width: 80px;
        position: absolute;
        bottom: 20px;
        cursor: pointer;
      "
      autoplay
      loop
      src="https://lottie.host/dbc6e249-fd68-4359-944b-b435e75d91e1/y2iEXbwqmO.lottie"
    />
  </div>
</template>

<style scoped>
.dark .hero {
  @apply bg-[url('../assets/bg-dark.svg')];
}

/* Bounce untuk foto */

.bounce-enter-active {
  animation: bounce-in 1.5s;
}
.bounce-leave-active {
  animation: bounce-in 1s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(1.2);
  }
  100% {
    transform: scale(1);
  }
}
</style>
