<template>
  <nav class="fixed top-0 left-0 right-0 z-50 bg-black/90 backdrop-blur-md border-b border-slate-800 soft-shadow">
    <div class="container-max">
      <div class="flex items-center justify-between h-16 md:h-20">
        <a 
          href="#home" 
          @click.prevent="scrollTo('#home')"
          class="text-xl md:text-2xl font-bold bg-gradient-to-r from-blue-400 to-indigo-400 bg-clip-text text-transparent hover:opacity-80 transition-opacity"
        >
          Ansu Konneh
        </a>
        
        <!-- Hamburger menu button - visible on all screen sizes -->
        <button 
          @click="mobileMenuOpen = !mobileMenuOpen"
          class="p-2 rounded-lg text-slate-300 hover:bg-slate-800 transition-colors"
          aria-label="Toggle menu"
        >
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path v-if="!mobileMenuOpen" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            <path v-else stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>
      
      <!-- Menu - visible when hamburger is clicked -->
      <div v-if="mobileMenuOpen" class="pb-4 border-t border-slate-800 mt-2 pt-4">
        <a 
          v-for="item in navItems" 
          :key="item.path"
          :href="item.path" 
          @click.prevent="scrollTo(item.path); mobileMenuOpen = false"
          class="block py-2 text-slate-300 hover:text-indigo-400 font-medium transition-colors"
          :class="{ 'text-indigo-400': activeSection === item.path }"
        >
          {{ item.label }}
        </a>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const mobileMenuOpen = ref(false)
const activeSection = ref('#home')

const navItems = [
  { label: 'Home', path: '#home' },
  { label: 'About', path: '#about' },
  { label: 'Skills', path: '#skills' },
  { label: 'Projects', path: '#projects' },
  { label: 'Experience', path: '#experience' },
  { label: 'Contact', path: '#contact' },
]

const scrollTo = (path) => {
  const element = document.querySelector(path)
  if (element) {
    const offset = 80
    const elementPosition = element.getBoundingClientRect().top + window.pageYOffset
    const offsetPosition = elementPosition - offset
    
    window.scrollTo({
      top: offsetPosition,
      behavior: 'smooth'
    })
  }
}

const handleScroll = () => {
  const sections = navItems.map(item => item.path.substring(1))
  const scrollPosition = window.pageYOffset + 100
  
  for (const section of sections) {
    const element = document.getElementById(section)
    if (element) {
      const offsetTop = element.offsetTop
      const offsetBottom = offsetTop + element.offsetHeight
      
      if (scrollPosition >= offsetTop && scrollPosition < offsetBottom) {
        activeSection.value = `#${section}`
        break
      }
    }
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
  handleScroll()
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

