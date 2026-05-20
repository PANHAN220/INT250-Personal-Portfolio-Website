<template>
  <section id="contact" class="py-28 bg-white dark:bg-gray-950 transition-colors duration-300">
    <div class="max-w-6xl mx-auto px-8">

      <!-- Title -->
      <div class="reveal mb-20">
        <h2 class="text-4xl md:text-5xl font-bold text-gray-900 dark:text-white mb-3">Get in Touch</h2>
        <p class="text-gray-400 dark:text-gray-500">Interested in working together or have a question? Feel free to drop a message.</p>
      </div>

      <!-- 2-column layout: left info + right form -->
      <div class="grid md:grid-cols-2 gap-16 items-start">

        <!-- Left: Description + contact info -->
        <div class="reveal delay-1">
          <h3 class="text-2xl font-bold text-gray-900 dark:text-white mb-6 leading-snug">
            Let's build something minimal<br />and beautiful together.
          </h3>
          <p class="text-gray-500 dark:text-gray-400 leading-relaxed mb-10">
            I'm currently looking for internship or cooperative education opportunities
            starting next semester. Whether you have an open role or just want to say hi,
            I'll try my best to get back to you!
          </p>

          <div class="space-y-5">
            <div class="flex items-center gap-4">
              <div class="w-11 h-11 rounded-2xl bg-blue-50 dark:bg-blue-900/30 flex items-center justify-center text-blue-500 text-lg flex-shrink-0">✉</div>
              <div>
                <p class="font-semibold text-gray-900 dark:text-white text-sm">Email</p>
                <p class="text-gray-500 dark:text-gray-400 text-sm">hello@example.com</p>
              </div>
            </div>
            <div class="flex items-center gap-4">
              <div class="w-11 h-11 rounded-2xl bg-green-50 dark:bg-green-900/30 flex items-center justify-center text-green-500 text-lg flex-shrink-0">📍</div>
              <div>
                <p class="font-semibold text-gray-900 dark:text-white text-sm">Location</p>
                <p class="text-gray-500 dark:text-gray-400 text-sm">Bangkok, Thailand (Open to Remote)</p>
              </div>
            </div>
          </div>
        </div>

        <!-- Right: Contact form -->
        <div class="reveal delay-2">
          <div class="p-8 rounded-3xl border border-gray-100 dark:border-gray-800 bg-gray-50 dark:bg-gray-900">
            <div class="space-y-5">

              <!-- Name + Email row -->
              <div class="grid grid-cols-2 gap-4">
                <div>
                  <label class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2">Name</label>
                  <input
                    v-model="form.name"
                    type="text"
                    placeholder="John Doe"
                    class="w-full px-4 py-3 rounded-xl border border-gray-200 dark:border-gray-700 bg-white dark:bg-gray-800 text-gray-900 dark:text-white placeholder-gray-400 text-sm outline-none focus:border-blue-400 dark:focus:border-blue-500 transition-colors"
                  />
                </div>
                <div>
                  <label class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2">Email</label>
                  <input
                    v-model="form.email"
                    type="email"
                    placeholder="john@example.com"
                    class="w-full px-4 py-3 rounded-xl border border-gray-200 dark:border-gray-700 bg-white dark:bg-gray-800 text-gray-900 dark:text-white placeholder-gray-400 text-sm outline-none focus:border-blue-400 dark:focus:border-blue-500 transition-colors"
                  />
                </div>
              </div>

              <!-- Message -->
              <div>
                <label class="block text-sm font-medium text-gray-700 dark:text-gray-300 mb-2">Message</label>
                <textarea
                  v-model="form.message"
                  rows="5"
                  placeholder="Your message here..."
                  class="w-full px-4 py-3 rounded-xl border border-gray-200 dark:border-gray-700 bg-white dark:bg-gray-800 text-gray-900 dark:text-white placeholder-gray-400 text-sm outline-none focus:border-blue-400 dark:focus:border-blue-500 transition-colors resize-none"
                ></textarea>
              </div>

              <!-- Submit button -->
              <button
                @click="submitForm"
                class="w-full py-3.5 rounded-xl bg-gray-900 dark:bg-white text-white dark:text-gray-900 font-semibold text-sm flex items-center justify-center gap-2 hover:bg-gray-700 dark:hover:bg-gray-100 transition-colors"
              >
                <span v-if="!sent">Send Message</span>
                <span v-else>Message Sent! ✓</span>
              </button>

            </div>
          </div>
        </div>

      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, reactive } from 'vue'

const sent = ref(false)
const form = reactive({ name: '', email: '', message: '' })

function submitForm() {
  if (!form.name || !form.email || !form.message) return
  // จำลองการส่ง (ใน production ต่อกับ emailjs หรือ backend จริงๆ)
  sent.value = true
  setTimeout(() => {
    sent.value = false
    form.name = ''
    form.email = ''
    form.message = ''
  }, 3000)
}
</script>
