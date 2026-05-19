<template>
  <section id="about" class="py-28 bg-white dark:bg-gray-950 transition-colors duration-300">
    <div class="max-w-6xl mx-auto px-8">

      <!-- Title -->
      <div class="reveal mb-20">
        <h2 class="text-4xl md:text-5xl font-bold text-gray-900 dark:text-white mb-3">About Me</h2>
        <p class="text-gray-400 dark:text-gray-500 text-base">Get to know me better, my background, and what drives me as a developer.</p>
      </div>

      <!-- Content: Left text + Right cards -->
      <div class="grid md:grid-cols-2 gap-16 items-start">

        <!-- Left: Bio text -->
        <div class="space-y-6">
          <p class="reveal delay-1 text-gray-600 dark:text-gray-400 text-lg leading-relaxed">
            Hello! I'm an enthusiastic IT student specializing in
            frontend web development. My journey into tech started
            with a curiosity about how websites are built, which
            quickly blossomed into a deep passion for coding and design.
          </p>
          <p class="reveal delay-2 text-gray-600 dark:text-gray-400 text-lg leading-relaxed">
            I believe in the power of minimalism — not just in
            design, but in code structure. A well-organized codebase
            and a clean user interface go hand in hand to create
            exceptional digital products. When I'm not coding, I'm
            exploring new design systems or reading about web accessibility.
          </p>
        </div>

        <!-- Right: Info cards (3 cards like screenshot) -->
        <div class="grid grid-cols-2 gap-4">

          <!-- Background card -->
          <div class="reveal delay-1 col-span-1 p-6 rounded-2xl border border-gray-100 dark:border-gray-800 hover:border-gray-200 dark:hover:border-gray-700 hover:shadow-md transition-all duration-300">
            <div class="w-10 h-10 rounded-xl bg-blue-50 dark:bg-blue-900/30 flex items-center justify-center mb-4">
              <span class="text-blue-500 text-lg">👤</span>
            </div>
            <h3 class="font-bold text-gray-900 dark:text-white mb-2">Background</h3>
            <p class="text-gray-500 dark:text-gray-400 text-sm leading-relaxed">IT Student with a passion for building clean, user-centric interfaces.</p>
          </div>

          <!-- Interests card -->
          <div class="reveal delay-2 col-span-1 p-6 rounded-2xl border border-gray-100 dark:border-gray-800 hover:border-gray-200 dark:hover:border-gray-700 hover:shadow-md transition-all duration-300">
            <div class="w-10 h-10 rounded-xl bg-green-50 dark:bg-green-900/30 flex items-center justify-center mb-4">
              <span class="text-green-500 text-lg">&lt;/&gt;</span>
            </div>
            <h3 class="font-bold text-gray-900 dark:text-white mb-2">Interests</h3>
            <p class="text-gray-500 dark:text-gray-400 text-sm leading-relaxed">Frontend Architecture, UI/UX Design, and Performance Optimization.</p>
          </div>

          <!-- Aspirations card (half width) -->
          <div class="reveal delay-3 col-span-1 p-6 rounded-2xl border border-gray-100 dark:border-gray-800 hover:border-gray-200 dark:hover:border-gray-700 hover:shadow-md transition-all duration-300">
            <div class="w-10 h-10 rounded-xl bg-purple-50 dark:bg-purple-900/30 flex items-center justify-center mb-4">
              <span class="text-purple-500 text-lg">💻</span>
            </div>
            <h3 class="font-bold text-gray-900 dark:text-white mb-2">Aspirations</h3>
            <p class="text-gray-500 dark:text-gray-400 text-sm leading-relaxed">Seeking internship opportunities to apply skills in a real-world environment.</p>
          </div>

          <!-- Education card -->
          <div class="reveal delay-4 col-span-1 p-6 rounded-2xl border border-gray-100 dark:border-gray-800 hover:border-gray-200 dark:hover:border-gray-700 hover:shadow-md transition-all duration-300">
            <div class="w-10 h-10 rounded-xl bg-orange-50 dark:bg-orange-900/30 flex items-center justify-center mb-4">
              <span class="text-orange-500 text-lg">🎓</span>
            </div>
            <h3 class="font-bold text-gray-900 dark:text-white mb-2">Education</h3>
            <p class="text-gray-500 dark:text-gray-400 text-sm leading-relaxed">B.S. Information Technology, KMUTT — GPA 3.8</p>
          </div>

        </div>
      </div>
    </div>
  </section>
</template>

<script setup></script>
