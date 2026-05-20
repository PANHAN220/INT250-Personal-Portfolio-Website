<template>
  <section id="projects" class="py-28 bg-white dark:bg-gray-950 transition-colors duration-300">
    <div class="max-w-6xl mx-auto px-8">

      <!-- Title -->
      <div class="reveal mb-20">
        <h2 class="text-4xl md:text-5xl font-bold text-gray-900 dark:text-white mb-3">Selected Projects</h2>
        <p class="text-gray-400 dark:text-gray-500 max-w-xl">A showcase of my recent work, highlighting frontend architecture and UI/UX implementation.</p>
      </div>

      <!-- Project cards grid -->
      <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
        <div
          v-for="(project, i) in projects"
          :key="project.title"
          :class="`reveal delay-${i + 1}`"
          class="group flex flex-col rounded-2xl border-4 border-gray-100 dark:border-gray-800 overflow-hidden hover:shadow-xl hover:border-gray-200 dark:hover:border-gray-700 transition-all duration-300 hover:-translate-y-1"
        >
          <!-- Project image -->
          <div class="relative overflow-hidden bg-gray-100 dark:bg-gray-800 aspect-video">
            <img
              :src="project.image"
              :alt="project.title"
              class="w-full h-full object-cover object-top group-hover:scale-110 transition-transform duration-700 ease-in-out"
            />

            <div class="absolute inset-0 bg-gray-900/10 group-hover:bg-transparent transition-colors duration-300"></div>
          </div>

          <!-- Project info -->
          <div class="p-6 flex flex-col ">
            <p class="text-blue-500 text-sm font-medium mb-2">{{ project.role }}</p>
            <h3 class="font-bold text-gray-900 dark:text-white text-lg mb-3">{{ project.title }}</h3>
            <p class="text-gray-500 dark:text-gray-400 text-sm leading-relaxed mb-5 flex-grow">{{ project.description }}</p>

            <!-- Tech tags -->
            <div class="flex flex-wrap gap-2 mt-auto">
              <span
                v-for="tech in project.tech"
                :key="tech"
                class="px-3 py-1 rounded-lg border border-gray-200 dark:border-gray-700 text-gray-600 dark:text-gray-400 text-xs font-medium"
              >
                {{ tech }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const projects = [
  {
    title: 'Visual Memory Test',
    role: 'Team Lead',
    description: 'A web-based game designed to test and improve visual memory skills. Built as part of the INT250 course with a focus on interactive UI and state management.',
    tech: ['Vue.js', 'Tailwind CSS', 'Vite'],
    image: '/assets/VisualMemoryTest.png'
  },
  {
    title: 'Shortly Website',
    role: 'Frontend Developer',
    description: 'A URL shortening landing page implementation featuring a responsive design and API integration for generating short links.',
    tech: ['Vue.js', 'Tailwind CSS'],
    image: '/assets/ShortlyWebsite.png'
  },
  {
    title: 'Fylo Website',
    role: 'Frontend Developer',
    description: 'A landing page for a file storage service including a custom color picker feature, demonstrating advanced CSS and layout skills.',
    tech: ['Vue.js', 'Tailwind CSS', 'Interactivity'],
    image: '/assets/FyloWebsite.png'
  }
]
</script>
