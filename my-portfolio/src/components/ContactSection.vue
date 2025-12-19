<template>
  <section id="contact" class="section-padding bg-slate-900">
    <div class="container-max">
      <h2 class="text-4xl md:text-5xl font-bold text-center mb-4 bg-gradient-to-r from-blue-400 to-indigo-400 bg-clip-text text-transparent">
        Get In Touch
      </h2>
      <p class="text-xl text-slate-300 text-center mb-12 max-w-2xl mx-auto">
        I'm always open to discussing new projects, opportunities, or just connecting with fellow developers and students.
      </p>
      
      <div class="grid md:grid-cols-2 gap-12 items-start">
        <!-- Contact Form -->
        <div class="soft-shadow-lg rounded-2xl p-8 bg-slate-800 border border-slate-700">
          <h3 class="text-2xl font-bold text-slate-100 mb-6">Send me a message</h3>
          <form @submit.prevent="handleSubmit" class="space-y-4">
            <div>
              <label for="name" class="block text-sm font-medium text-slate-300 mb-2">Name</label>
              <input 
                type="text" 
                id="name" 
                v-model="form.name"
                required
                class="w-full px-4 py-3 rounded-lg bg-slate-900 border border-slate-600 text-slate-100 placeholder-slate-500 focus:ring-2 focus:ring-indigo-500 focus:border-transparent transition-all"
                placeholder="Your name"
              />
            </div>
            <div>
              <label for="email" class="block text-sm font-medium text-slate-300 mb-2">Email</label>
              <input 
                type="email" 
                id="email" 
                v-model="form.email"
                required
                class="w-full px-4 py-3 rounded-lg bg-slate-900 border border-slate-600 text-slate-100 placeholder-slate-500 focus:ring-2 focus:ring-indigo-500 focus:border-transparent transition-all"
                placeholder="your.email@example.com"
              />
            </div>
            <div>
              <label for="subject" class="block text-sm font-medium text-slate-300 mb-2">Subject</label>
              <input 
                type="text" 
                id="subject" 
                v-model="form.subject"
                required
                class="w-full px-4 py-3 rounded-lg bg-slate-900 border border-slate-600 text-slate-100 placeholder-slate-500 focus:ring-2 focus:ring-indigo-500 focus:border-transparent transition-all"
                placeholder="What's this about?"
              />
            </div>
            <div>
              <label for="message" class="block text-sm font-medium text-slate-300 mb-2">Message</label>
              <textarea 
                id="message" 
                v-model="form.message"
                required
                rows="6"
                class="w-full px-4 py-3 rounded-lg bg-slate-900 border border-slate-600 text-slate-100 placeholder-slate-500 focus:ring-2 focus:ring-indigo-500 focus:border-transparent transition-all resize-none"
                placeholder="Tell me about your project, opportunity, or just say hello!"
              ></textarea>
            </div>
            <button 
              type="submit"
              :disabled="isSubmitting"
              class="w-full px-8 py-4 bg-gradient-to-r from-blue-600 to-indigo-600 text-white rounded-lg font-semibold text-lg soft-shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-200 disabled:opacity-50 disabled:cursor-not-allowed disabled:transform-none"
            >
              {{ isSubmitting ? 'Sending...' : 'Send Message' }}
            </button>
          </form>
          <div v-if="formStatus" class="mt-4 p-4 rounded-lg" :class="formStatus.type === 'success' ? 'bg-green-900 text-green-300' : 'bg-red-900 text-red-300'">
            {{ formStatus.message }}
          </div>
        </div>
        
        <!-- Social Links & Info -->
        <div class="space-y-6">
          <div class="soft-shadow-lg rounded-2xl p-8 bg-slate-800 border border-slate-700">
            <h3 class="text-2xl font-bold text-slate-100 mb-6">Connect with me</h3>
            <div class="space-y-4">
              <a 
                v-for="social in socialLinks" 
                :key="social.name"
                :href="social.url" 
                target="_blank"
                rel="noopener noreferrer"
                class="flex items-center space-x-4 p-4 bg-slate-900 rounded-lg soft-shadow hover:shadow-lg transform hover:-translate-y-1 transition-all duration-200 group border border-slate-700"
              >
                <div class="flex-1">
                  <div class="font-semibold text-slate-200 group-hover:text-indigo-400 transition-colors">
                    {{ social.name }}
                  </div>
                  <div class="text-sm text-slate-400">{{ social.handle }}</div>
                </div>
                <svg class="w-5 h-5 text-slate-500 group-hover:text-indigo-400 transition-colors" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
                </svg>
              </a>
            </div>
          </div>
          
          <div class="soft-shadow-lg rounded-2xl p-8 bg-slate-800 border border-slate-700">
            <h3 class="text-2xl font-bold text-slate-100 mb-4">Quick Info</h3>
            <div class="space-y-3 text-slate-300">
              <div class="flex items-start">
                <span class="text-xl mr-3">📍</span>
                <div>
                  <strong class="text-slate-100">Location:</strong><br>
                  Liberia
                </div>
              </div>
              <div class="flex items-start">
                <span class="text-xl mr-3">🎓</span>
                <div>
                  <strong class="text-slate-100">Education:</strong><br>
                  Forensic Science (Dual University Program)
                </div>
              </div>
              <div class="flex items-start">
                <span class="text-xl mr-3">💼</span>
                <div>
                  <strong class="text-slate-100">Status:</strong><br>
                  Open to opportunities and collaborations
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const form = ref({
  name: '',
  email: '',
  subject: '',
  message: '',
})

const isSubmitting = ref(false)
const formStatus = ref(null)

const socialLinks = [
  { name: 'GitHub', handle: '@ansukonneh', url: 'https://github.com' },
  { name: 'LinkedIn', handle: 'Ansu Konneh', url: 'https://linkedin.com' },
  { name: 'Facebook', handle: 'Ansu M. Konneh', url: 'https://facebook.com' },
  { name: 'Email', handle: 'ansukonneh028@gmail.com', url: 'mailto:ansukonneh028@gmail.com' },
]

const handleSubmit = async () => {
  isSubmitting.value = true
  formStatus.value = null
  
  // Simulate form submission (replace with actual API call)
  setTimeout(() => {
    isSubmitting.value = false
    formStatus.value = {
      type: 'success',
      message: 'Thank you for your message! I\'ll get back to you soon.'
    }
    form.value = { name: '', email: '', subject: '', message: '' }
    
    // Clear message after 5 seconds
    setTimeout(() => {
      formStatus.value = null
    }, 5000)
  }, 1500)
}
</script>

