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
          class="group rounded-2xl border border-gray-100 dark:border-gray-800 overflow-hidden hover:shadow-xl hover:border-gray-200 dark:hover:border-gray-700 transition-all duration-300 hover:-translate-y-1"
        >
          <!-- Project image -->
          <div class="overflow-hidden bg-gray-100 dark:bg-gray-800">
            <img
              :src="project.image"
              :alt="project.title"
              class="w-full h-48 object-cover group-hover:scale-105 transition-transform duration-500"
            />
          </div>

          <!-- Project info -->
          <div class="p-6">
            <p class="text-blue-500 text-sm font-medium mb-2">{{ project.role }}</p>
            <h3 class="font-bold text-gray-900 dark:text-white text-lg mb-3">{{ project.title }}</h3>
            <p class="text-gray-500 dark:text-gray-400 text-sm leading-relaxed mb-5">{{ project.description }}</p>

            <!-- Tech tags -->
            <div class="flex flex-wrap gap-2">
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
    title: 'Finance Dashboard UI',
    role: 'Frontend Developer',
    description: 'A clean and modern dashboard interface for financial data tracking. Features responsive charts, dark mode support, and customizable widgets.',
    tech: ['Vue.js', 'Tailwind CSS', 'Chart.js'],
    image: 'https://placehold.co/600x300/f8fafc/94a3b8?text=Finance+Dashboard'
  },
  {
    title: 'Dark Mode Component Library',
    role: 'Sole Creator',
    description: 'A comprehensive UI component library built from scratch, prioritizing accessibility and seamless theme switching capabilities.',
    tech: ['Vue.js', 'Tailwind CSS', 'Storybook'],
    image: 'https://placehold.co/600x300/0f172a/6366f1?text=Component+Library'
  },
  {
    title: 'Task Management App',
    role: 'Fullstack Developer',
    description: 'A minimalist mobile-first web app for daily task management. Includes drag-and-drop functionality and offline support.',
    tech: ['React', 'Motion', 'Supabase'],
    image: 'https://placehold.co/600x300/1e293b/38bdf8?text=Task+App'
  }
]
</script>
