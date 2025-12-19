<template>
  <div class="soft-shadow-lg rounded-2xl p-6 md:p-8 bg-slate-900 border border-slate-700 hover:shadow-xl transform hover:-translate-y-1 transition-all duration-300">
    <div class="flex flex-col md:flex-row md:items-start md:justify-between mb-4">
      <div class="flex items-start space-x-4 flex-1">
        <div class="text-4xl">{{ item.icon }}</div>
        <div class="flex-1">
          <h3 class="text-2xl font-bold text-slate-100 mb-1">{{ item.title }}</h3>
          <p class="text-lg text-indigo-400 font-semibold mb-1">{{ item.organization }}</p>
          <div class="flex flex-wrap items-center gap-2 mt-2">
            <span class="px-3 py-1 bg-blue-900 text-blue-300 text-xs font-semibold rounded-full">
              {{ item.type }}
            </span>
            <span class="text-sm text-slate-400">{{ item.period }}</span>
          </div>
        </div>
      </div>
    </div>
    
    <p class="text-slate-300 mb-4 leading-relaxed">{{ item.description }}</p>
    
    <ul class="space-y-2">
      <li 
        v-for="(highlight, index) in item.highlights" 
        :key="index"
        class="flex items-start text-slate-300"
      >
        <span class="text-indigo-400 mr-2 mt-1">✓</span>
        <span>{{ highlight }}</span>
      </li>
    </ul>
  </div>
</template>

<script setup>
defineProps({
  item: Object,
})
</script>

