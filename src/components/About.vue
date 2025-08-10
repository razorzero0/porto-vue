<script setup>
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
</script>

<template>
  <section
    id="about"
    class="py-16 bg-gray-50 dark:bg-gray-900 min-h-[100vh] flex flex-col justify-center items-center"
  >
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <!-- Kalimat tambahan di atas -->
      <div class="mb-12 text-center">
        <h2
          class="text-3xl md:text-5xl font-bold uppercase relative inline-block tracking-widest text-secondary dark:text-slate-50"
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

      <div class="grid md:grid-cols-2 gap-12">
        <!-- Kolom 1: About Me -->
        <div class="">
          <h2 class="text-2xl font-bold mb-4 title">Get to know me!</h2>
          <p
            class="text-gray-600 dark:text-gray-300 leading-relaxed mb-4 text-xl"
          >
            I’m passionate about <span class="font-bold">learning</span> and
            exploring the world of web development. With experience in both
            <span class="font-bold">teaching</span> and building projects, I
            enjoy turning ideas into
            <span class="font-bold">functional</span> and
            <span class="font-bold">user-friendly</span> web solutions. I’m
            always excited to grow my skills and take on new challenges.
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
        <div class="">
          <h2 class="text-2xl font-bold mb-5 sm:text-center title">
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
    </div>
  </section>
</template>

<style scoped></style>
