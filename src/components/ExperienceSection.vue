<template>
  <section id="experience" class="py-28 bg-gray-50 dark:bg-gray-900 transition-colors duration-300">
    <div class="max-w-6xl mx-auto px-8">

      <!-- Title -->
      <div class="reveal mb-20">
        <h2 class="text-4xl md:text-5xl font-bold text-gray-900 dark:text-white mb-3">Experience & Activities</h2>
        <p class="text-gray-400 dark:text-gray-500">My academic background, practical experience, and notable achievements.</p>
      </div>

      <!-- Timeline -->
      <div class="relative">
        <!-- Vertical line -->
        <div class="absolute left-6 top-0 bottom-0 w-px bg-gray-200 dark:bg-gray-700 hidden md:block"></div>

        <div class="space-y-12">
          <div
            v-for="(item, i) in experiences"
            :key="item.title"
            :class="`reveal delay-${i + 1}`"
            class="relative flex flex-col md:flex-row gap-6 md:gap-10"
          >
            <!-- Icon circle on the timeline -->
            <div class="flex-shrink-0 relative z-10">
              <div class="w-12 h-12 rounded-full border-2 border-gray-200 dark:border-gray-700 bg-white dark:bg-gray-900 flex items-center justify-center text-gray-500 dark:text-gray-400 text-lg shadow-sm">
                {{ item.icon }}
              </div>
            </div>

            <!-- Content -->
            <div class="flex-1 p-6 rounded-2xl border border-gray-100 dark:border-gray-800 bg-white dark:bg-gray-900 shadow-sm hover:shadow-md transition-all duration-300">
              <div class="flex flex-col md:flex-row md:items-start md:justify-between gap-2 mb-2">
                <h3 class="font-bold text-gray-900 dark:text-white text-xl">{{ item.title }}</h3>
                <span class="inline-flex items-center px-3 py-1 rounded-full bg-gray-100 dark:bg-gray-800 text-gray-500 dark:text-gray-400 text-xs font-medium flex-shrink-0">
                  {{ item.period }}
                </span>
              </div>
              <p class="text-blue-500 font-medium text-sm mb-3">{{ item.org }}</p>
              <p class="text-gray-500 dark:text-gray-400 leading-relaxed text-sm">{{ item.description }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const experiences = [
  {
    icon: '🎓',
    title: 'B.S. in Information Technology',
    org: 'University of Technology',
    period: '2023 - Present',
    description: 'Focusing on Software Engineering, Web Development, and UX Design. Currently holding a 3.8 GPA.'
  },
  {
    icon: '💼',
    title: 'Frontend Developer Trainee',
    org: 'Tech Startup Academy',
    period: 'Jun 2025 - Aug 2025',
    description: 'Participated in an intensive bootcamp, building several SPA projects using Vue.js and React. Collaborated with a team of 4 to deliver a final capstone project.'
  },
  {
    icon: '🏆',
    title: '1st Place — Campus Hackathon',
    org: 'University Tech Club',
    period: 'Nov 2024',
    description: 'Developed an accessibility-first student portal prototype within 48 hours. Led the frontend implementation using Tailwind CSS.'
  },
  {
    icon: '📜',
    title: 'Meta Frontend Developer Certificate',
    org: 'Coursera',
    period: 'Aug 2024',
    description: 'Completed a professional certificate program covering React fundamentals, responsive design, and web accessibility best practices.'
  }
]
</script>
