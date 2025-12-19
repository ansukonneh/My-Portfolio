<template>
  <footer class="bg-slate-900 text-slate-300 py-8">
    <div class="container-max text-center">
      <p class="mb-4">
        &copy; {{ currentYear }} Ansu Konneh. All rights reserved.
      </p>
      <p class="text-sm text-slate-500">
        Connecting technology with purpose, one project at a time.
      </p>
    </div>
  </footer>
</template>

<script setup>
import { computed } from 'vue'

const currentYear = computed(() => new Date().getFullYear())
</script>

