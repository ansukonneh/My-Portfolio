<template>
  <div class="soft-shadow-lg rounded-2xl p-6 bg-slate-900 border border-slate-700 hover:transform hover:-translate-y-2 transition-all duration-300">
    <div class="flex items-center mb-4">
      <span class="text-3xl mr-3">{{ icon }}</span>
      <h3 class="text-xl font-bold text-slate-100">{{ title }}</h3>
    </div>
    <div class="space-y-3">
      <div 
        v-for="skill in skills" 
        :key="skill.name"
        class="flex items-center justify-between"
      >
        <span class="text-slate-300 font-medium">{{ skill.name }}</span>
        <span 
          class="px-3 py-1 rounded-full text-xs font-semibold"
          :class="getLevelClass(skill.level)"
        >
          {{ skill.level }}
        </span>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: String,
  skills: Array,
  icon: String,
  color: String,
})

const getLevelClass = (level) => {
  const classes = {
    'Advanced': 'bg-green-900 text-green-300',
    'Intermediate': 'bg-blue-900 text-blue-300',
    'Learning': 'bg-purple-900 text-purple-300',
  }
  return classes[level] || 'bg-gray-800 text-gray-300'
}
</script>

