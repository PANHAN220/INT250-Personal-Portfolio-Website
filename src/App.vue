<template>
  <div class="bg-white dark:bg-gray-950 text-gray-900 dark:text-gray-100 transition-colors duration-300 min-h-screen">
    <NavBar :isDark="isDark" @toggle-dark="toggleDark" />
    <HeroSection />
    <AboutSection />
    <SkillsSection />
    <ProjectsSection />
    <ExperienceSection />
    <ContactSection />
    <FooterSection />
  </div>
</template>

<script setup>
import { ref, onMounted, nextTick, watch } from 'vue'
import NavBar          from './components/NavBar.vue'
import HeroSection     from './components/HeroSection.vue'
import AboutSection    from './components/AboutSection.vue'
import SkillsSection   from './components/SkillsSection.vue'
import ProjectsSection from './components/ProjectsSection.vue'
import ExperienceSection from './components/ExperienceSection.vue'
import ContactSection  from './components/ContactSection.vue'
import FooterSection   from './components/FooterSection.vue'

// Theme Logic
const getInitialTheme = () => {
  const savedTheme = localStorage.getItem('theme')
  if (savedTheme) {
    return savedTheme === 'dark'
  }
  return window.matchMedia('(prefers-color-scheme: dark)').matches
}

const isDark = ref(getInitialTheme())

const toggleDark = () => {
  isDark.value = !isDark.value
  console.log('Theme toggled. isDark:', isDark.value)
}

// Watch for changes and update document class and localStorage
watch(isDark, (val) => {
  if (val) {
    document.documentElement.classList.add('dark')
    localStorage.setItem('theme', 'dark')
  } else {
    document.documentElement.classList.remove('dark')
    localStorage.setItem('theme', 'light')
  }
  console.log('HTML classes:', document.documentElement.classList.value)
}, { immediate: true })

onMounted(async () => {
  // Animation logic
  await nextTick()
  const elements = document.querySelectorAll('.reveal')
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((e) => {
        if (e.isIntersecting) e.target.classList.add('visible')
      })
    },
    { threshold: 0.08 }
  )
  elements.forEach((el) => observer.observe(el))
})
</script>
