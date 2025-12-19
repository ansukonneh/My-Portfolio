<template>
  <section id="skills" class="section-padding bg-black">
    <div class="container-max">
      <h2 class="text-4xl md:text-5xl font-bold text-center mb-16 bg-gradient-to-r from-blue-400 to-indigo-400 bg-clip-text text-transparent">
        Skills & Technologies
      </h2>
      
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
        <SkillCategory 
          title="Backend Development"
          :skills="backendSkills"
          color="from-blue-500 to-indigo-500"
        />
        <SkillCategory 
          title="Frontend Development"
          :skills="frontendSkills"
          color="from-purple-500 to-pink-500"
        />
        <SkillCategory 
          title="Digital Forensics"
          :skills="forensicsSkills"
          color="from-green-500 to-teal-500"
        />
        <SkillCategory 
          title="Machine Learning"
          :skills="mlSkills"
          color="from-orange-500 to-red-500"
        />
        <SkillCategory 
          title="Tools & Others"
          :skills="toolsSkills"
          color="from-indigo-500 to-purple-500"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import SkillCategory from './SkillCategory.vue'

const backendSkills = [
  { name: 'Javascript', level: 'Intermediate' },
  { name: 'NodeJS', level: 'Beginner' },
  { name: 'REST APIs', level: 'Learning' },
  { name: 'Database Design', level: 'Learning' },
]

const frontendSkills = [
  { name: 'Vue.js 3', level: 'Intermediate' },
  { name: 'TailwindCSS', level: 'Intermediate' },
  { name: 'JavaScript', level: 'Intermediate' },
  { name: 'HTML/CSS', level: 'Advanced' },
]

const forensicsSkills = [
  { name: 'Digital Evidence', level: 'Learning' },
  { name: 'Forensic Tools', level: 'Learning' },
  { name: 'Cybersecurity Basics', level: 'Learning' },  
]

const mlSkills = [
  { name: 'TinyML Basics', level: 'Learning' },
  { name: 'Python ML Libraries', level: 'Learning' },
]

const toolsSkills = [
  { name: 'Git & GitHub', level: 'Intermediate' },
  { name: 'API Design', level: 'Intermediate' },
  { name: 'Problem Solving', level: 'Advanced' },
]

</script>

