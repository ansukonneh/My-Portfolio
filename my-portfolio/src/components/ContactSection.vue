<template>
  <section id="contact" class="section-padding bg-slate-900">
    <div class="container-max">
      <SectionHeading>Get In Touch</SectionHeading>
      <p class="text-xl text-slate-300 text-center mb-12 max-w-2xl mx-auto">
        I'm always open to discussing new projects, opportunities, or just connecting with fellow developers and students.
      </p>
      <div class="grid md:grid-cols-2 gap-12 items-start">
        <ContactForm />
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
                <div><strong class="text-slate-100">Location:</strong><br>Liberia</div>
              </div>
              <div class="flex items-start">
                <span class="text-xl mr-3">🎓</span>
                <div><strong class="text-slate-100">Education:</strong><br>Forensic Science & Computer Science</div>
              </div>
              <div class="flex items-start">
                <span class="text-xl mr-3">💼</span>
                <div><strong class="text-slate-100">Status:</strong><br>Open to opportunities and collaborations</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import SectionHeading from './SectionHeading.vue'
import ContactForm from './ContactForm.vue'

const socialLinks = [
  { name: 'GitHub', handle: '@ansukonneh', url: 'https://github.com' },
  { name: 'LinkedIn', handle: 'Ansu Konneh', url: 'https://linkedin.com' },
  { name: 'Facebook', handle: 'Ansu M. Konneh', url: 'https://facebook.com' },
  { name: 'Email', handle: 'ansukonneh028@gmail.com', url: 'mailto:ansukonneh028@gmail.com' },
]
</script>

