<template>
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
        class="w-full px-8 py-4 bg-gradient-to-r from-blue-600 to-indigo-600 text-white rounded-lg font-semibold text-lg soft-shadow-lg hover:shadow-xl hover:shadow-indigo-500/50 transform hover:-translate-y-1 transition-all duration-200"
      >
        Send Message
      </button>
    </form>
    <div v-if="formStatus" class="mt-4 p-4 rounded-lg border-2 bg-green-900/50 border-green-500/50 text-green-300">
      <div class="flex items-center gap-2">
        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7" />
        </svg>
        <span>{{ formStatus.message }}</span>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

const form = ref({ name: '', email: '', subject: '', message: '' })
const formStatus = ref(null)

const handleSubmit = () => {
  const { name, email, subject, message } = form.value
  const mailtoLink = `mailto:ansukonneh028@gmail.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(`From: ${name} (${email})\n\n${message}`)}`
  window.location.href = mailtoLink
  
  formStatus.value = {
    type: 'success',
    message: 'Opening your email client... If it doesn\'t open, please email me directly at ansukonneh028@gmail.com'
  }
  form.value = { name: '', email: '', subject: '', message: '' }
  setTimeout(() => formStatus.value = null, 5000)
}
</script>

