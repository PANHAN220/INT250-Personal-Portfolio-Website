<template>
  <section id="hero" class="min-h-screen flex items-center pt-20 bg-white dark:bg-gray-950 transition-colors duration-300">
    <div class="max-w-6xl mx-auto px-8 py-20 w-full">
      <div class="flex flex-col md:flex-row items-center justify-between gap-16">

        <!-- LEFT: Text -->
        <div class="flex-1 max-w-xl">

          <!-- Badge -->
          <div class="reveal inline-flex items-center gap-2 px-4 py-1.5 rounded-full border border-blue-200 dark:border-blue-800 bg-blue-50 dark:bg-blue-950/50 text-blue-600 dark:text-blue-400 text-sm font-medium mb-8">
            <span class="w-1.5 h-1.5 rounded-full bg-blue-500 animate-pulse"></span>
            Available for Opportunities
          </div>

          <!-- Headline -->
          <h1 class="reveal delay-1 text-5xl md:text-6xl font-bold text-gray-900 dark:text-white leading-tight mb-6">
            Hi, I'm a <span class="text-blue-500">{{ displayedRole }}</span><span class="cursor text-blue-500">|</span>
            <br />crafting minimal<br />digital experiences.
          </h1>

          <!-- Sub text -->
          <p class="reveal delay-2 text-gray-500 dark:text-gray-400 text-base leading-relaxed mb-10 max-w-md">
            I specialize in building responsive, user-centric web applications
            using modern technologies like Vue, Tailwind CSS, and more.
          </p>

          <!-- Buttons -->
          <div class="reveal delay-3 flex flex-wrap items-center gap-4 mb-12">
            <a href="#projects" class="flex items-center gap-2 px-6 py-3 bg-gray-900 dark:bg-white text-white dark:text-gray-900 rounded-lg font-semibold text-sm hover:bg-gray-700 dark:hover:bg-gray-100 transition-colors">
              View Projects <span>→</span>
            </a>
            <a href="#contact" class="px-6 py-3 rounded-lg border border-gray-300 dark:border-gray-600 text-gray-700 dark:text-gray-300 font-semibold text-sm hover:border-gray-500 dark:hover:border-gray-400 transition-colors">
              Contact Me
            </a>
          </div>

          <!-- Social links -->
          <div class="reveal delay-4 flex items-center gap-5 text-sm text-gray-400 dark:text-gray-500">
            <span>Connect with me:</span>
            <a href="https://github.com" target="_blank" class="hover:text-gray-700 dark:hover:text-gray-200 transition-colors text-xl">⌥</a>
            <a href="https://linkedin.com" target="_blank" class="hover:text-gray-700 dark:hover:text-gray-200 transition-colors text-xl">in</a>
            <a href="mailto:hello@example.com" class="hover:text-gray-700 dark:hover:text-gray-200 transition-colors text-xl">✉</a>
          </div>
        </div>

        <!-- RIGHT: Photo card -->
        <div class="reveal delay-2 relative flex-shrink-0">
          <!-- Glow background -->
          <div class="absolute -inset-4 rounded-3xl bg-gradient-to-br from-blue-100 to-purple-100 dark:from-blue-900/20 dark:to-purple-900/20 blur-2xl"></div>

          <!-- Photo -->
          <div class="relative">
            <img
              src="https://placehold.co/340x400/1a1a2e/ffffff?text=Your+Photo"
              alt="Profile"
              class="relative w-72 md:w-80 rounded-2xl object-cover shadow-2xl grayscale hover:grayscale-0 transition-all duration-500"
            />
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const roles = ['Frontend Developer', 'IT Student']
const displayedRole = ref('')
let roleIndex = 0, charIndex = 0, isDeleting = false

function typeEffect() {
  const current = roles[roleIndex]
  displayedRole.value = isDeleting ? current.slice(0, charIndex - 1) : current.slice(0, charIndex + 1)
  isDeleting ? charIndex-- : charIndex++

  if (!isDeleting && charIndex === current.length) {
    setTimeout(() => { isDeleting = true; typeEffect() }, 1800)
    return
  }
  if (isDeleting && charIndex === 0) {
    isDeleting = false
    roleIndex = (roleIndex + 1) % roles.length
  }
  setTimeout(typeEffect, isDeleting ? 50 : 90)
}

onMounted(() => setTimeout(typeEffect, 600))
</script>
