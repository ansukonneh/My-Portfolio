<template>
  <nav class="fixed top-0 left-0 right-0 z-50 bg-black/90 backdrop-blur-md border-b border-slate-800 soft-shadow">
    <div class="max-w-6xl mx-auto px-4 md:px-8">
      <div class="flex items-center justify-between h-16 md:h-20">
        <router-link 
          to="/"
          class="text-xl md:text-2xl font-bold bg-gradient-to-r from-blue-400 to-indigo-400 bg-clip-text text-transparent hover:opacity-80 transition-opacity"
        >
          Ansu Konneh
        </router-link>
        
        <!-- Desktop Navigation Links -->
        <div class="hidden md:flex desktop-nav items-center gap-3 lg:gap-5">
          <router-link 
            v-for="item in navItems" 
            :key="item.path"
            :to="item.path"
            class="text-slate-300 hover:text-indigo-400 font-medium transition-colors px-3 py-2 rounded-lg hover:bg-slate-800/50 whitespace-nowrap"
            :class="{ 'text-indigo-400 bg-slate-800/30': route.path === item.path }"
          >
            {{ item.label }}
          </router-link>
        </div>
        
        <!-- Mobile Hamburger Button -->
        <button 
          @click="mobileMenuOpen = !mobileMenuOpen"
          class="md:hidden p-2 rounded-lg text-slate-300 hover:bg-slate-800 transition-colors"
          aria-label="Toggle menu"
        >
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path v-if="!mobileMenuOpen" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
            <path v-else stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
          </svg>
        </button>
      </div>
      
      <!-- Mobile Menu Dropdown -->
      <div v-if="mobileMenuOpen" class="md:hidden pb-4 border-t border-slate-800 mt-2 pt-4">
        <router-link 
          v-for="item in navItems" 
          :key="item.path"
          :to="item.path"
          @click="mobileMenuOpen = false"
          class="block py-2 text-slate-300 hover:text-indigo-400 font-medium transition-colors"
          :class="{ 'text-indigo-400': route.path === item.path }"
        >
          {{ item.label }}
        </router-link>
      </div>
    </div>
  </nav>
</template>

<script setup>
import { ref } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const mobileMenuOpen = ref(false)

const navItems = [
  { label: 'Home', path: '/' },
  { label: 'About', path: '/about' },
  { label: 'Projects', path: '/projects' },
  { label: 'Contact', path: '/contact' },
]
</script>

<style scoped>
/* Ensure desktop navigation is visible on screens 768px and wider */
@media (min-width: 768px) {
  .desktop-nav {
    display: flex !important;
  }
}
</style>

