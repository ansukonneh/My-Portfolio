<template>
  <section id="home" class="min-h-screen flex items-center justify-center section-padding pt-32 md:pt-40 bg-black">
    <div class="container-max text-center">
      <div class="animate-fade-in">
        <h1 class="text-5xl md:text-7xl lg:text-8xl font-bold mb-6 bg-gradient-to-r from-blue-400 via-indigo-400 to-purple-400 bg-clip-text text-transparent leading-tight">
          Ansu Konneh
        </h1>
        <p class="text-xl md:text-2xl lg:text-3xl text-slate-300 mb-4 font-medium">
          Forensic Science Student • Frontend Developer • Tech Entrepreneur
        </p>
        <p class="text-lg md:text-xl text-slate-400 mb-12 max-w-2xl mx-auto">
          Building digital solutions while pursuing justice through technology. 
          Connecting Liberian youth with opportunities, one line of code at a time.
        </p>
        <div class="flex flex-col sm:flex-row gap-4 justify-center items-center">
          <a 
            href="#projects" 
            @click.prevent="scrollToProjects"
            class="px-8 py-4 bg-gradient-to-r from-blue-600 to-indigo-600 text-white rounded-lg font-semibold text-lg soft-shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-200"
          >
            View My Work
          </a>
          <a 
            href="#contact" 
            @click.prevent="scrollToContact"
            class="px-8 py-4 bg-slate-900 text-indigo-400 border-2 border-indigo-400 rounded-lg font-semibold text-lg soft-shadow hover:shadow-lg transform hover:-translate-y-1 transition-all duration-200"
          >
            Get In Touch
          </a>
        </div>
      </div>
      
      <!-- Decorative elements -->
      <div class="mt-16 flex justify-center space-x-2">
        <div class="w-2 h-2 bg-blue-500 rounded-full animate-bounce" style="animation-delay: 0s"></div>
        <div class="w-2 h-2 bg-indigo-500 rounded-full animate-bounce" style="animation-delay: 0.2s"></div>
        <div class="w-2 h-2 bg-purple-500 rounded-full animate-bounce" style="animation-delay: 0.4s"></div>
      </div>
    </div>
  </section>
</template>

<script setup>
const scrollToProjects = () => {
  const element = document.querySelector('#projects')
  if (element) {
    const offset = 80
    const elementPosition = element.getBoundingClientRect().top + window.pageYOffset
    const offsetPosition = elementPosition - offset
    window.scrollTo({ top: offsetPosition, behavior: 'smooth' })
  }
}

const scrollToContact = () => {
  const element = document.querySelector('#contact')
  if (element) {
    const offset = 80
    const elementPosition = element.getBoundingClientRect().top + window.pageYOffset
    const offsetPosition = elementPosition - offset
    window.scrollTo({ top: offsetPosition, behavior: 'smooth' })
  }
}
</script>

<style scoped>
@keyframes fade-in {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fade-in 1s ease-out;
}
</style>

