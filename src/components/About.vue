<script setup>
import { ref, onMounted, onUnmounted } from "vue";

const skills = [
  "HTML",
  "CSS",
  "JavaScript",
  "React",
  "Vue.js",
  "Tailwind CSS",
  "Node.js",
  "PHP",
  "Laravel",
  "SQL",
  "REST API",
  "Git",
];

const showAnim = ref(false);

onMounted(() => {
  const target = document.getElementById("about");

  if (target) {
    const observer = new IntersectionObserver(
      (entries) => {
        entries.forEach((entry) => {
          if (entry.isIntersecting) {
            showAnim.value = true; // trigger animasi
            observer.unobserve(target); // stop observe setelah sekali animasi
          }
        });
      },
      { threshold: 0.6 } // 20% terlihat baru jalan animasi
    );

    observer.observe(target);
  }
});
</script>

<template>
  <section
    id="about"
    class="pb-16 pt-20 bg-gray-50 dark:bg-gray-900 min-h-[100vh] flex flex-col justify-center items-center"
  >
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <transition name="slideUp">
        <!-- Bungkus biar muncul hanya jika showAnim true -->
        <div v-if="showAnim" class="mb-12 text-center">
          <h2
            class="text-3xl md:text-4xl font-bold uppercase relative inline-block tracking-widest text-secondary dark:text-slate-50"
          >
            About Me
          </h2>
          <!-- Garis pendek di bawah -->
          <div class="w-20 h-1 bg-primary mx-auto rounded my-10"></div>

          <p
            class="text-gray-600 dark:text-gray-300 max-w-3xl mx-auto text-xl text-shadow-gray-300"
          >
            Here you will find more information about me, what I do, and my
            current skills mostly in terms of programming and technology.
          </p>
        </div>
      </transition>
      <transition name="slideUp">
        <div class="grid md:grid-cols-2 gap-12" v-if="showAnim">
          <!-- Kolom 1: About Me -->
          <div>
            <h2 class="text-2xl font-bold mb-4 text-primary">
              Get to know me!
            </h2>
            <p
              class="text-gray-600 dark:text-gray-300 leading-relaxed mb-4 text-xl"
            >
              I’m passionate about <strong>learning</strong> and exploring the
              world of web development. With experience in both
              <strong>teaching</strong> and building projects, I enjoy turning
              ideas into <strong>functional</strong> and
              <strong>user-friendly</strong> web solutions. I’m always excited
              to grow my skills and take on new challenges.
            </p>

            <p class="leading-relaxed mb-4 text-xl">
              You can connect with me on
              <a
                href="https://www.linkedin.com/in/muhammad-ainun-yanuar-syam/"
                target="_blank"
                class="link"
                >LinkedIn</a
              >, follow my work on
              <a
                href="https://github.com/razorzero0/"
                target="_blank"
                class="link"
                >GitHub</a
              >, or see my daily updates on
              <a
                href="https://www.instagram.com/m_ainunnn/#"
                target="_blank"
                class="link"
                >Instagram</a
              >.
            </p>
            <p class="text-gray-600 dark:text-gray-300 leading-relaxed text-xl">
              I’m currently open to exciting job opportunities, collaborations,
              and freelance projects. Feel free to reach out if you think we can
              create something great together.
            </p>
          </div>

          <!-- Kolom 2: My Skills -->
          <div>
            <h2 class="text-2xl font-bold mb-5 sm:text-center text-primary">
              My Skills
            </h2>
            <div class="grid grid-cols-2 sm:grid-cols-3 gap-5">
              <div
                v-for="(skill, index) in skills"
                :key="index"
                class="bg-white dark:bg-gray-800 shadow rounded-lg px-5 py-6 text-center font-medium text-gray-800 dark:text-gray-200 hover:shadow-light-vue transition cursor-pointer"
              >
                {{ skill }}
              </div>
            </div>
          </div>
        </div>
      </transition>
    </div>
  </section>
</template>

<style scoped>
/*  Slide Up + Fade */
.slideUp-enter-active {
  transition: all 0.5s ease-in;
  transition-delay: 0.2s;
}
.slideUp-leave-active {
  transition: all 0.5s ease-in;
}
.slideUp-enter-from {
  opacity: 0;
  transform: translateY(60px);
}
.slideUp-enter-to {
  opacity: 1;
  transform: translateY(0);
}
.slideUp-leave-from {
  opacity: 1;
  transform: translateY(0);
}
.slideUp-leave-to {
  opacity: 0;
  transform: translateY(60px);
}
</style>
