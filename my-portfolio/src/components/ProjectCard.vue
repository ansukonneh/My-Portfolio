<template>
  <div 
    class="soft-shadow-lg rounded-2xl overflow-hidden bg-gradient-to-br from-slate-800 to-slate-900 border border-slate-700/50 hover:border-indigo-500/50 hover:shadow-2xl hover:shadow-indigo-500/20 transform hover:-translate-y-2 transition-all duration-300"
    :class="{ 'ring-2 ring-indigo-500 ring-opacity-50': project.highlight }"
  >
    <!-- Project Image -->
    <div class="h-64 bg-gradient-to-br from-blue-600 via-indigo-600 to-purple-600 relative overflow-hidden group">
      <img 
        v-if="project.image && project.image !== '/project-placeholder.png'"
        :src="project.image" 
        :alt="project.title"
        class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
        @error="handleImageError"
      />
      <div v-else class="absolute inset-0 flex items-center justify-center bg-gradient-to-br from-blue-600 via-indigo-600 to-purple-600">
        <div class="text-white text-6xl opacity-30">{{ getProjectIcon(project.title) }}</div>
      </div>
      <div class="absolute inset-0 bg-gradient-to-t from-black/60 via-transparent to-transparent opacity-0 group-hover:opacity-100 transition-opacity duration-300"></div>
      <div v-if="project.status === 'In Progress'" class="absolute top-4 right-4 z-10">
        <span class="px-3 py-1 bg-yellow-500/90 backdrop-blur-sm text-white text-xs font-semibold rounded-full shadow-lg">In Progress</span>
      </div>
      <div v-else-if="project.status === 'Active'" class="absolute top-4 right-4 z-10">
        <span class="px-3 py-1 bg-green-500/90 backdrop-blur-sm text-white text-xs font-semibold rounded-full shadow-lg">Active</span>
      </div>
    </div>
    
    <!-- Project Content -->
    <div class="p-6">
      <h3 class="text-2xl font-bold text-slate-100 mb-3">{{ project.title }}</h3>
      <p class="text-slate-300 mb-4 leading-relaxed">{{ project.description }}</p>
      
      <!-- Tech Stack Badges -->
      <div class="flex flex-wrap gap-2 mb-5">
        <span 
          v-for="tech in project.techStack" 
          :key="tech"
          class="px-3 py-1.5 bg-gradient-to-r from-slate-700 to-slate-800 text-blue-300 text-xs font-semibold rounded-lg border border-slate-600/50 hover:border-blue-500/50 transition-all duration-200 shadow-sm"
        >
          {{ tech }}
        </span>
      </div>
      
      <!-- Action Buttons -->
      <div class="flex gap-3">
        <button 
          v-if="project.githubUrl"
          @click="() => window.open(project.githubUrl, '_blank')"
          class="flex-1 px-4 py-2.5 bg-gradient-to-r from-blue-600 to-indigo-600 text-white rounded-lg font-medium hover:from-blue-500 hover:to-indigo-500 hover:shadow-lg hover:shadow-blue-500/50 transition-all duration-200 transform hover:-translate-y-0.5"
        >
          View Code
        </button>
        <button 
          v-else
          class="flex-1 px-4 py-2.5 bg-gradient-to-r from-blue-600 to-indigo-600 text-white rounded-lg font-medium hover:from-blue-500 hover:to-indigo-500 hover:shadow-lg hover:shadow-blue-500/50 transition-all duration-200 transform hover:-translate-y-0.5"
        >
          View Details
        </button>
        <button 
          v-if="project.liveUrl"
          @click="() => window.open(project.liveUrl, '_blank')"
          class="px-4 py-2.5 border-2 border-slate-600 text-slate-300 rounded-lg font-medium hover:bg-slate-700 hover:border-indigo-500 hover:text-indigo-400 transition-all duration-200"
          title="View Live Demo"
        >
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 6H6a2 2 0 00-2 2v10a2 2 0 002 2h10a2 2 0 002-2v-4M14 4h6m0 0v6m0-6L10 14" />
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  project: Object,
})

const getProjectIcon = (title) => {
  const icons = {
    'JobZ Platform': '💼',
    'Church Management System API': '⛪',
    'Movie Database App': '🎬',
    'Music Player': '🎵',
  }

  return icons[title] || '📁'
}

const handleImageError = (event) => {
  // Fallback to gradient background if image fails to load
  event.target.style.display = 'none'
}
</script>

