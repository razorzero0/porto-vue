<script setup>
import { ref, onMounted } from "vue";

const isOpen = ref(false);
const isDark = ref(false);

const toggleMenu = () => {
  isOpen.value = !isOpen.value;
};

const toggleDark = () => {
  isDark.value = !isDark.value;
  const html = document.documentElement;
  if (isDark.value) {
    html.classList.add("dark");
  } else {
    html.classList.remove("dark");
  }
};
</script>

<template>
  <nav class="bg-white dark:bg-gray-900 shadow fixed top-0 left-0 w-full z-50">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div class="flex items-center justify-between h-16">
        <!-- Logo kiri -->
        <div class="flex-shrink-0 flex items-center">
          <div
            class="text-xl font-bold text-gray-900 dark:text-white cursor-pointer relative"
          >
            <p class="nav-link">Ainun Porto</p>
          </div>
        </div>
        <!-- Menu tengah -->
        <div class="hidden md:flex flex-1 justify-center">
          <div class="flex gap-3 space-x-4">
            <a
              href="#hero"
              class="relative text-gray-700 dark:text-gray-200 px-3 py-2 rounded-md text-sm font-medium nav-link"
            >
              Welcome
            </a>
            <a
              href="#about"
              class="relative text-gray-700 dark:text-gray-200 px-3 py-2 rounded-md text-sm font-medium nav-link"
            >
              About
            </a>
            <a
              href="#"
              class="relative text-gray-700 dark:text-gray-200 px-3 py-2 rounded-md text-sm font-medium nav-link"
            >
              Project
            </a>
            <a
              href="#"
              class="relative text-gray-700 dark:text-gray-200 px-3 py-2 rounded-md text-sm font-medium nav-link"
            >
              Experience
            </a>
          </div>
        </div>
        <!-- Kanan: Toggle dark mode & hamburger -->
        <div class="flex items-center">
          <!-- Toggle dark mode -->
          <button
            @click="toggleDark"
            class="mr-2 p-2 rounded-full bg-gray-200 dark:bg-gray-700 text-gray-700 dark:text-gray-200 hover:bg-gray-300 dark:hover:bg-gray-600 focus:outline-none transition"
          >
            <span v-if="!isDark">
              <!-- Sun icon -->
              <svg
                class="h-5 w-5"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                viewBox="0 0 24 24"
              >
                <circle cx="12" cy="12" r="5" />
                <path
                  d="M12 1v2M12 21v2M4.22 4.22l1.42 1.42M18.36 18.36l1.42 1.42M1 12h2M21 12h2M4.22 19.78l1.42-1.42M18.36 5.64l1.42-1.42"
                />
              </svg>
            </span>
            <span v-else>
              <!-- Moon icon -->
              <svg
                class="h-5 w-5"
                fill="none"
                stroke="currentColor"
                stroke-width="2"
                viewBox="0 0 24 24"
              >
                <path d="M21 12.79A9 9 0 1111.21 3a7 7 0 109.79 9.79z" />
              </svg>
            </span>
          </button>
          <!-- Hamburger -->
          <div class="-mr-2 flex md:hidden">
            <button
              @click="toggleMenu"
              type="button"
              class="inline-flex items-center justify-center p-2 rounded-md text-gray-700 dark:text-gray-200 hover:text-primary dark:hover:text-primary hover:bg-gray-100 dark:hover:bg-gray-800 focus:outline-none focus:ring-2 focus:ring-inset focus:ring-primary"
            >
              <svg
                class="h-6 w-6"
                :class="{ hidden: isOpen, block: !isOpen }"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M4 6h16M4 12h16M4 18h16"
                />
              </svg>
              <svg
                class="h-6 w-6"
                :class="{ block: isOpen, hidden: !isOpen }"
                xmlns="http://www.w3.org/2000/svg"
                fill="none"
                viewBox="0 0 24 24"
                stroke="currentColor"
              >
                <path
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  stroke-width="2"
                  d="M6 18L18 6M6 6l12 12"
                />
              </svg>
            </button>
          </div>
        </div>
      </div>
    </div>
    <!-- Mobile menu -->
    <Transition name="slide-fade">
      <div class="md:hidden" v-if="isOpen">
        <div class="px-2 pt-2 pb-3 space-y-1 flex flex-col items-center">
          <a
            href="#hero"
            class="block text-gray-700 dark:text-gray-200 hover:text-primary px-3 py-2 rounded-md text-base font-medium"
            >Welcome</a
          >
          <a
            href="#about"
            class="block text-gray-700 dark:text-gray-200 hover:text-primary px-3 py-2 rounded-md text-base font-medium"
            >About</a
          ><a
            href="#"
            class="text-gray-700 dark:text-gray-200 hover:text-primary px-3 py-2 rounded-md text-sm font-medium"
            >Projects</a
          >
          <a
            href="#"
            class="text-gray-700 dark:text-gray-200 hover:text-primary px-3 py-2 rounded-md text-sm font-medium"
            >Experience</a
          >
        </div>
      </div>
    </Transition>
  </nav>
</template>

<style lang="scss" scoped>
/* Animasi transisi slide-fade */
.slide-fade-enter-active,
.slide-fade-leave-active {
  transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
}
.slide-fade-enter-from {
  opacity: 0;
  transform: translateY(-10px);
}
.slide-fade-enter-to {
  opacity: 1;
  transform: translateY(0);
}
.slide-fade-leave-from {
  opacity: 1;
  transform: translateY(0);
}
.slide-fade-leave-to {
  opacity: 0;
  transform: translateY(-10px);
}
</style>
