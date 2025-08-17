<template>
  <section class="py-16 bg-gray-50 dark:bg-gray-900" id="contact">
    <div class="max-w-7xl mx-auto px-6">
      <!-- Title -->
      <div class="mb-12 text-center">
        <h2
          class="text-3xl md:text-4xl font-bold uppercase relative inline-block tracking-widest text-secondary dark:text-slate-50"
        >
          Contact Me
        </h2>
        <div class="w-20 h-1 bg-primary mx-auto rounded my-10"></div>
        <p
          class="text-gray-600 dark:text-gray-300 max-w-3xl mx-auto text-xl text-shadow-gray-300"
        >
          If you have any questions or just want to say hi, feel free to reach
          out!
        </p>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
        <!-- Form -->
        <form class="space-y-6">
          <div>
            <label
              for="name"
              class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2"
            >
              Name
            </label>
            <input
              id="name"
              type="text"
              placeholder="Enter your name"
              class="w-full px-4 py-3 rounded-xl border border-gray-300 dark:border-gray-600 bg-transparent dark:bg-gray-800 text-gray-900 dark:text-gray-100 focus:border-primary focus:ring-2 focus:ring-primary/40 outline-none transition"
            />
          </div>

          <div>
            <label
              for="email"
              class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2"
            >
              Email
            </label>
            <input
              id="email"
              type="email"
              placeholder="Enter your email"
              class="w-full px-4 py-3 rounded-xl border border-gray-300 dark:border-gray-600 bg-transparent dark:bg-gray-800 text-gray-900 dark:text-gray-100 focus:border-primary focus:ring-2 focus:ring-primary/40 outline-none transition"
            />
          </div>

          <div>
            <label
              for="message"
              class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2"
            >
              Message
            </label>
            <textarea
              id="message"
              rows="4"
              placeholder="Write your message..."
              class="w-full px-4 py-3 rounded-xl border border-gray-300 dark:border-gray-600 bg-transparent dark:bg-gray-800 text-gray-900 dark:text-gray-100 focus:border-primary focus:ring-2 focus:ring-primary/40 outline-none transition"
            ></textarea>
          </div>

          <button
            type="submit"
            class="w-full bg-primary text-white py-3 px-6 rounded-xl font-semibold hover:bg-primary/90 transition"
          >
            Send Message
          </button>
        </form>

        <!-- Image -->
        <div class="hidden md:block">
          <img
            src="/src/assets/contact.svg"
            alt="Contact illustration"
            class="w-full max-h-[500px] object-cover rounded-2xl"
          />
        </div>
      </div>
    </div>
  </section>
</template>
