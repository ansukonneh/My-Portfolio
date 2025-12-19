<template>
  <div 
    class="soft-shadow-lg rounded-2xl overflow-hidden bg-slate-800 border border-slate-700 hover:shadow-2xl transform hover:-translate-y-2 transition-all duration-300"
    :class="{ 'ring-2 ring-indigo-500': project.highlight }"
  >
    <!-- Project Image Placeholder -->
    <div class="h-48 bg-gradient-to-br from-blue-600 via-indigo-600 to-purple-600 relative overflow-hidden">
      <div class="absolute inset-0 flex items-center justify-center">
        <div class="text-white text-6xl opacity-30">{{ getProjectIcon(project.title) }}</div>
      </div>
      <div v-if="project.status === 'In Progress'" class="absolute top-4 right-4">
        <span class="px-3 py-1 bg-yellow-600 text-white text-xs font-semibold rounded-full">In Progress</span>
      </div>
      <div v-else-if="project.status === 'Active'" class="absolute top-4 right-4">
        <span class="px-3 py-1 bg-green-600 text-white text-xs font-semibold rounded-full">Active</span>
      </div>
    </div>
    
    <!-- Project Content -->
    <div class="p-6">
      <h3 class="text-2xl font-bold text-slate-100 mb-3">{{ project.title }}</h3>
      <p class="text-slate-300 mb-4 leading-relaxed">{{ project.description }}</p>
      
      <!-- Tech Stack Badges -->
      <div class="flex flex-wrap gap-2 mb-4">
        <span 
          v-for="tech in project.techStack" 
          :key="tech"
          class="px-3 py-1 bg-slate-700 text-blue-300 text-xs font-semibold rounded-full border border-slate-600"
        >
          {{ tech }}
        </span>
      </div>
      
      <!-- Action Buttons -->
      <div class="flex gap-3">
        <button class="flex-1 px-4 py-2 bg-gradient-to-r from-blue-600 to-indigo-600 text-white rounded-lg font-medium hover:shadow-lg transition-all duration-200">
          View Details
        </button>
        <button class="px-4 py-2 border border-slate-600 text-slate-300 rounded-lg font-medium hover:bg-slate-700 transition-colors">
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
    'JobZ Platform': '',
    'Church Management System API': '',
    'Movie Database App': '',
    'Music Player': '',
  }

  return icons[title] || ''
}
</script>

