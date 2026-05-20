<template>
  <section id="skills" class="py-28 bg-gray-50 dark:bg-gray-900 transition-colors duration-300">
    <div class="max-w-6xl mx-auto px-8">

      <!-- Title -->
      <div class="reveal mb-20">
        <h2 class="text-4xl md:text-5xl font-bold text-gray-900 dark:text-white mb-3">Skills & Expertise</h2>
        <p class="text-gray-400 dark:text-gray-500">My technical toolkit and the technologies I use to build scalable web applications.</p>
      </div>

      <!-- 4 category cards like screenshot -->
      <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-5">
        <div
          v-for="(category, i) in skillCategories"
          :key="category.title"
          :class="`reveal delay-${i + 1}`"
          class="p-6 rounded-2xl border border-gray-200 dark:border-gray-700 bg-white dark:bg-gray-800 hover:shadow-md hover:border-gray-300 dark:hover:border-gray-600 transition-all duration-300"
        >
          <!-- Category title -->
          <h3 class="font-semibold text-gray-900 dark:text-white mb-5 pb-4 border-b border-gray-100 dark:border-gray-700">
            {{ category.title }}
          </h3>

          <!-- Skill tags -->
          <div class="flex flex-wrap gap-2">
            <span
              v-for="skill in category.skills"
              :key="skill"
              class="px-3 py-1.5 rounded-lg bg-gray-100 dark:bg-gray-700 text-gray-700 dark:text-gray-300 text-sm hover:bg-gray-200 dark:hover:bg-gray-600 transition-colors cursor-default"
            >
              {{ skill }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const skillCategories = [
  {
    title: 'Languages',
    skills: ['JavaScript', 'Java', 'HTML5', 'CSS3', 'Python']
  },
  {
    title: 'Frameworks & Libraries',
    skills: ['Vue.js', 'Tailwind CSS', 'DaisyUi', 'Node.js']
  },
  {
    title: 'Tools & Platforms',
    skills: ['Git', 'GitHub', 'Vercel', 'Figma', 'VS Code']
  },
  {
    title: 'Soft Skills',
    skills: ['Problem Solving', 'Team Collaboration', 'Communication', 'Adaptability']
  }
]
</script>
