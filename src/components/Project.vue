<script setup>
import { ref } from "vue";

const projects = [
  {
    title: "Website Portfolio",
    image: "https://images.pexels.com/photos/326503/pexels-photo-326503.jpeg",
    description:
      "A modern portfolio website built with Vue, Tailwind, and Vite to showcase personal projects and skills.",
    tech: ["Vue", "Tailwind", "Vite"],
  },
  {
    title: "E-Commerce App",
    image: "https://images.pexels.com/photos/326503/pexels-photo-326503.jpeg",
    description:
      "A scalable e-commerce platform with product listings, cart, and payment system.",
    tech: ["React", "Node.js", "MongoDB"],
  },
  {
    title: "Dashboard Analytics",
    image: "https://images.pexels.com/photos/326503/pexels-photo-326503.jpeg",
    description:
      "An advanced dashboard for visualizing analytics data with interactive charts.",
    tech: ["Next.js", "Chart.js", "Prisma"],
  },
];

const selectedProject = ref(null);

function openModal(project) {
  selectedProject.value = project;
}
function closeModal() {
  selectedProject.value = null;
}
</script>

<template>
  <section class="pb-12 pt-20 px-6 dark:bg-gray-900" id="project">
    <div class="mb-14 text-center">
      <h2
        class="text-3xl md:text-4xl font-bold uppercase relative inline-block tracking-widest text-secondary dark:text-slate-50"
      >
        My Projects
      </h2>
      <div class="w-20 h-1 bg-primary mx-auto rounded my-6"></div>

      <p
        class="text-gray-600 dark:text-gray-300 max-w-3xl mx-auto text-xl text-shadow-gray-300"
      >
        Here are some of the projects I've worked on recently. Click to learn
        more!
      </p>
    </div>

    <!-- Responsive grid -->
    <div
      class="max-w-7xl mx-auto grid grid-cols-1 md:grid-cols-3 gap-8 justify-items-center"
    >
      <div
        v-for="(project, index) in projects"
        :key="index"
        class="relative group rounded-2xl overflow-hidden shadow-lg w-full max-w-md cursor-pointer"
        @click="openModal(project)"
      >
        <!-- Background Image -->
        <div
          class="h-64 w-full bg-cover bg-center relative filter grayscale group-hover:grayscale-0 transition duration-500"
          :style="{ backgroundImage: `url(${project.image})` }"
        >
          <!-- Overlay Gradient -->
          <div
            class="absolute inset-0 bg-gradient-to-b from-black/30 to-black/70 transition duration-500 group-hover:from-black/10 group-hover:to-black/40"
          ></div>

          <!-- Title -->
          <h3
            class="absolute bottom-6 left-6 text-xl font-semibold text-white z-10 group-hover:scale-105 transition-transform"
          >
            {{ project.title }}
          </h3>
        </div>

        <!-- Tech stack -->
        <div class="bg-white dark:bg-gray-800 px-4 py-3 flex flex-wrap gap-2">
          <span
            v-for="(tech, i) in project.tech"
            :key="i"
            class="text-xs px-3 py-1 rounded-full bg-primary text-white font-medium"
          >
            {{ tech }}
          </span>
        </div>
      </div>
    </div>

    <!-- Modal -->
    <transition name="fade-scale">
      <div
        v-if="selectedProject"
        class="fixed inset-0 flex items-center justify-center backdrop-blur-sm bg-gray-900/70 z-50"
        @click="closeModal"
      >
        <div
          class="bg-white dark:bg-gray-800 rounded-2xl p-10 max-w-2xl w-full mx-6 relative shadow-xl text-gray-900 dark:text-gray-100"
          @click.stop
        >
          <!-- Close Button -->
          <button
            class="absolute top-4 right-4 text-gray-600 hover:text-gray-900 dark:text-gray-300 dark:hover:text-gray-100 font-bold cursor-pointer"
            @click="closeModal"
          >
            ✕
          </button>

          <!-- Project Image -->
          <img
            :src="selectedProject.image"
            :alt="selectedProject.title"
            class="w-full h-40 md:h-64 object-cover rounded-xl mb-6"
          />

          <!-- Modal Title -->
          <h2 class="text-2xl font-bold mb-4">
            {{ selectedProject.title }}
          </h2>

          <!-- Modal Description -->
          <p
            class="text-gray-700 dark:text-gray-300 leading-relaxed mb-4 font-semibold"
          >
            {{ selectedProject.description }}
          </p>

          <!-- Tech Stack -->
          <div class="flex flex-wrap gap-3 mt-6 mb-6">
            <span
              v-for="(tech, index) in selectedProject.tech"
              :key="index"
              class="px-4 py-2 bg-primary hover:bg-primary-dark cursor-pointer rounded-xl text-sm text-white"
            >
              {{ tech }}
            </span>
          </div>

          <!-- Action Buttons -->
          <div class="flex flex-col md:flex-row justify-end gap-4">
            <button
              class="px-4 py-2 rounded-lg bg-gray-200 hover:bg-gray-300 dark:bg-gray-700 dark:hover:bg-gray-600 font-semibold"
              @click="closeModal"
            >
              Cancel
            </button>
            <button
              class="px-4 py-2 rounded-lg bg-primary text-white font-bold hover:opacity-90"
            >
              Visit Project
            </button>
          </div>
        </div>
      </div>
    </transition>
  </section>
</template>

<style scoped>
.fade-scale-enter-active,
.fade-scale-leave-active {
  transition: all 0.4s ease; /* lebih lama biar smooth */
}
.fade-scale-enter-from {
  opacity: 0;
  transform: scale(0.95); /* animasi zoom in */
}
.fade-scale-leave-to {
  opacity: 0;
  transform: scale(0.95);
}
</style>
