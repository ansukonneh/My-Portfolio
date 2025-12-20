<template>
  <section class="section-padding bg-black">
    <div class="container-max">
      <SectionHeading>Experience & Volunteering</SectionHeading>
      
      <div class="space-y-8">
        <ExperienceItem
          v-for="item in experienceItems"
          :key="item.id"
          :item="item"
        />
      </div>
      
      <div class="mt-12 text-center">
        <p class="text-slate-300 text-lg mb-6">
          Always open to new opportunities for growth, learning, and making an impact.
        </p>
        <router-link 
          to="/contact"
          class="inline-block px-8 py-3 bg-gradient-to-r from-blue-600 to-indigo-600 text-white rounded-lg font-semibold soft-shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-200"
        >
          Let's Connect
        </router-link>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import ExperienceItem from './ExperienceItem.vue'
import SectionHeading from './SectionHeading.vue'
import { experienceItems as items } from '../data/experience.js'

const experienceItems = ref(items)
</script>

