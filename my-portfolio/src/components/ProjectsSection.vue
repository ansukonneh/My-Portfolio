<template>
  <section id="projects" class="section-padding bg-slate-900">
    <div class="container-max">
      <h2 class="text-4xl md:text-5xl font-bold text-center mb-16 bg-gradient-to-r from-blue-400 to-indigo-400 bg-clip-text text-transparent">
        Featured Projects
      </h2>
      
      <div class="grid md:grid-cols-2 gap-8">
        <ProjectCard
          v-for="project in projects"
          :key="project.id"
          :project="project"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import ProjectCard from './ProjectCard.vue'

const projects = ref([
  {
    id: 1,
    title: 'JobZ Platform',
    description: 'A platform helping young Liberians find employment opportunities. Connecting job seekers with employers and creating pathways to economic empowerment.',
    techStack: ['Vue.js', 'Node.js', 'MongoDB', 'TailwindCSS'],
    image: '/project-placeholder.png',
    status: 'In Progress',
    highlight: true,
  },
  {
    id: 2,
    title: 'Church Management System API',
    description: 'A comprehensive backend API for managing church operations including member records, events, donations, and administrative tasks. Built as my capstone project.',
    techStack: ['Django', 'Python', 'REST API', 'JWT Auth', 'PostgreSQL'],
    image: '/project-placeholder.png',
    status: 'In Progress',
    highlight: true,
  },
  {
    id: 3,
    title: 'Movie Database App',
    description: 'A sample application for browsing and searching movies. Demonstrates API integration, state management, and modern UI/UX principles.',
    techStack: ['Vue.js', 'TailwindCSS', 'TMDB API', 'JavaScript'],
    image: '/project-placeholder.png',
    status: 'Active',
  },
  {
    id: 4,
    title: 'Music Player',
    description: 'A sleek music player application showcasing audio controls, playlist management, and responsive design. Built to explore frontend audio APIs.',
    techStack: ['Vue.js', 'TailwindCSS', 'JavaScript', 'Web Audio API'],
    image: 'my-portfolio/public/placeholder.jpg',
    status: 'Active',
  },
])
</script>

