<script setup>
import Navbar from "./components/Navbar.vue";
import { onMounted, onBeforeUnmount, reactive, computed } from "vue";

const pos = reactive({ x: 0, y: 0 });

function updatePosition(e) {
  pos.x = e.clientX;
  pos.y = e.clientY;
}

// Warna blur menyesuaikan tema
const blurBg = computed(() => {
  // Cek apakah elemen html punya class 'dark'
  const isDark = document.documentElement.classList.contains("dark");
  return isDark
    ? "radial-gradient(circle at center, rgba(59,130,246,0.25) 0%, rgba(59,130,246,0.0) 90%)" // biru gelap
    : "radial-gradient(circle at center, rgba(173,216,230,0.35) 0%, rgba(173,216,230,0.0) 90%)"; // lightblue
});

onMounted(() => {
  window.addEventListener("mousemove", updatePosition);
});

onBeforeUnmount(() => {
  window.removeEventListener("mousemove", updatePosition);
});
</script>

<template>
  <div
    class="relative min-h-screen bg-gray-50 dark:bg-gray-900 text-gray-800 dark:text-gray-100 overflow-hidden"
  >
    <!-- Lingkaran blur di background, blend ke konten -->
    <!-- <div
      class="pointer-events-none fixed inset-0 w-full h-full z-0"
      style="overflow: visible"
    >
      <div
        class="absolute w-[50vw] h-[50vw] max-w-none max-h-none rounded-full mix-blend-lighten dark:mix-blend-color-dodge"
        :style="{
          left: `calc(${pos.x}px - 25vw)`,
          top: `calc(${pos.y}px - 25vw)`,
          background: blurBg,
          filter: 'blur(120px)',
          pointerEvents: 'none',
        }"
      ></div>
    </div> -->
    <!-- Konten di atas blur -->
    <div class="relative">
      <Navbar />
      <main>
        <RouterView />
      </main>
    </div>
  </div>
</template>

<style scoped>
* {
  margin: 0;
  padding: 0;
}
</style>
