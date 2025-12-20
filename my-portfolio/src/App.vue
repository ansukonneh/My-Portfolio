<script setup>
import Navigation from './components/Navigation.vue'
import Footer from './components/Footer.vue'
</script>

<template>
  <div class="min-h-screen">
    <Navigation />
    <main>
      <router-view />
    </main>
    <Footer />
  </div>
</template>
