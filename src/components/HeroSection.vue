<template>
  <section id="hero" class="min-h-screen flex items-center pt-20 bg-white dark:bg-gray-950 transition-colors duration-300">
    <div class="max-w-6xl mx-auto px-8 py-20 w-full">
      <div class="flex flex-col md:flex-row items-center justify-between gap-16">

        <!-- LEFT: Text -->
        <div class="reveal flex-1 max-w-xl p-8 md:p-12 rounded-3xl border border-gray-100 dark:border-gray-800 bg-white/50 dark:bg-gray-900/50 backdrop-blur-sm shadow-sm">

          <!-- Badge -->
          <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full border border-blue-200 dark:border-blue-800 bg-blue-50 dark:bg-blue-950/50 text-blue-600 dark:text-blue-400 text-sm font-medium mb-8">
            <span class="w-1.5 h-1.5 rounded-full bg-blue-500 animate-pulse"></span>
            Available for Opportunities
          </div>

          <!-- Headline -->
          <h1 class="delay-1 text-5xl md:text-7xl font-bold text-gray-900 dark:text-white leading-tight mb-4">
            Sakdichot <span class="text-blue-600 dark:text-blue-400">Hanruangdej</span>
          </h1>

          <div class="delay-2 flex items-center gap-3 text-2xl md:text-3xl font-medium text-gray-600 dark:text-gray-300 mb-8">
            <span>I'm a</span>
            <span class="text-blue-500">{{ displayedRole }}</span><span class="cursor text-blue-500">|</span>
          </div>

          <!-- Sub text -->
          <p class="delay-2 text-gray-500 dark:text-gray-400 text-lg leading-relaxed mb-10 max-w-md">
            Currently studying at the School of Information Technology, King Mongkut's University of Technology Thonburi (KMUTT).
          </p>

          <!-- Buttons -->
          <div class="delay-3 flex flex-wrap items-center gap-4 mb-12">
            <a href="#projects" class="flex items-center gap-2 px-6 py-3 bg-gray-900 dark:bg-white text-white dark:text-gray-900 rounded-lg font-semibold text-sm hover:bg-gray-700 dark:hover:bg-gray-100 transition-colors">
              View Projects <span>→</span>
            </a>
            <a href="#contact" class="px-6 py-3 rounded-lg border border-gray-300 dark:border-gray-600 text-gray-700 dark:text-gray-300 font-semibold text-sm hover:border-gray-500 dark:hover:border-gray-400 transition-colors">
              Contact Me
            </a>
          </div>

          <!-- Social links -->
          <div class="delay-4 flex items-center gap-5 text-sm text-gray-400 dark:text-gray-500">
            <span>Connect with me:</span>
            <a href="https://github.com/PANHAN220" target="_blank" class="hover:text-gray-700 dark:hover:text-gray-200 transition-colors" title="GitHub">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                <path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"/>
              </svg>
            </a>
            <a href="https://linkedin.com" target="_blank" class="hover:text-gray-700 dark:hover:text-gray-200 transition-colors" title="LinkedIn">
              <svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
                <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z"/>
              </svg>
            </a>
            <a href="#contact" class="hover:text-gray-700 dark:hover:text-gray-200 transition-colors" title="Email">
              <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75"/>
              </svg>
            </a>
          </div>
        </div>

        <!-- RIGHT: Photo card -->
        <div class="reveal delay-2 relative flex-shrink-0 p-4 rounded-[2.5rem] border border-gray-100 dark:border-gray-800 bg-white dark:bg-gray-900 shadow-2xl animate-float">
          <!-- Glow background -->
          <div class="absolute -inset-4 rounded-3xl bg-gradient-to-br from-blue-100 to-purple-100 dark:from-blue-900/20 dark:to-purple-900/20 blur-2xl opacity-50 animate-pulse-glow"></div>

          <!-- Photo -->
          <div class="relative overflow-hidden rounded-[1.5rem]">
            <img
              src="/assets/MyProfile.jpg"
              alt="Profile"
              class="relative w-72 md:w-80 aspect-[4/5] rounded-2xl  hover:grayscale-0 hover:scale-105 transition-all duration-700 ease-out"
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

        <style scoped>
        @keyframes float {
        0% { transform: translateY(0px) rotate(0deg); }
        50% { transform: translateY(-15px) rotate(1deg); }
        100% { transform: translateY(0px) rotate(0deg); }
        }

        @keyframes pulse-glow {
        0%, 100% { opacity: 0.5; transform: scale(1); }
        50% { opacity: 0.8; transform: scale(1.1); }
        }

        .animate-float {
        animation: float 6s ease-in-out infinite;
        }

        .animate-pulse-glow {
        animation: pulse-glow 4s ease-in-out infinite;
        }

        .cursor {
        animation: blink 1s step-end infinite;
        }

        @keyframes blink {
        from, to { opacity: 1; }
        50% { opacity: 0; }
        }
        </style>
