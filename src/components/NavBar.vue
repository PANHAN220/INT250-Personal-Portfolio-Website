<template>
  <nav class="fixed top-0 left-0 right-0 z-50 bg-white/90 dark:bg-gray-950/90 backdrop-blur-sm border-b border-gray-100 dark:border-gray-800 transition-colors duration-300">
    <div class="max-w-6xl mx-auto px-8 py-5 flex items-center justify-between">

      <!-- Logo -->
      <a href="#hero" class="text-xl font-bold text-gray-900 dark:text-white tracking-tight">
        Port<span class="text-blue-500">folio.</span>
      </a>

      <!-- Desktop Links -->
      <ul class="hidden md:flex items-center gap-10 text-sm text-gray-600 dark:text-gray-400">
        <li><a href="#about"      class="hover:text-gray-900 dark:hover:text-white transition-colors">About</a></li>
        <li><a href="#skills"     class="hover:text-gray-900 dark:hover:text-white transition-colors">Skills</a></li>
        <li><a href="#projects"   class="hover:text-gray-900 dark:hover:text-white transition-colors">Projects</a></li>
        <li><a href="#experience" class="hover:text-gray-900 dark:hover:text-white transition-colors">Experience</a></li>
        <li><a href="#contact"    class="hover:text-gray-900 dark:hover:text-white transition-colors">Contact</a></li>
      </ul>

      <div class="flex items-center gap-3">
        <button @click="console.log('Toggle button clicked'); $emit('toggle-dark')" class="w-9 h-9 rounded-full border border-gray-200 dark:border-gray-700 flex items-center justify-center text-gray-500 dark:text-gray-400 hover:border-gray-400 dark:hover:border-gray-500 transition-colors text-sm">
          <span v-if="isDark">☀</span>
          <span v-else>☾</span>
        </button>
        <button @click="menuOpen = !menuOpen" class="md:hidden w-9 h-9 flex items-center justify-center rounded-full border border-gray-200 dark:border-gray-700 text-sm">
          {{ menuOpen ? '✕' : '☰' }}
        </button>
      </div>
    </div>

    <div v-if="menuOpen" class="md:hidden border-t border-gray-100 dark:border-gray-800 bg-white dark:bg-gray-950 px-8 py-5 flex flex-col gap-4 text-sm text-gray-600 dark:text-gray-400">
      <a href="#about"      @click="menuOpen=false" class="hover:text-gray-900 dark:hover:text-white transition-colors">About</a>
      <a href="#skills"     @click="menuOpen=false" class="hover:text-gray-900 dark:hover:text-white transition-colors">Skills</a>
      <a href="#projects"   @click="menuOpen=false" class="hover:text-gray-900 dark:hover:text-white transition-colors">Projects</a>
      <a href="#experience" @click="menuOpen=false" class="hover:text-gray-900 dark:hover:text-white transition-colors">Experience</a>
      <a href="#contact"    @click="menuOpen=false" class="hover:text-gray-900 dark:hover:text-white transition-colors">Contact</a>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'
defineProps(['isDark'])
defineEmits(['toggle-dark'])
const menuOpen = ref(false)
</script>
