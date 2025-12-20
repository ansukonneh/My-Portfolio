<template>
  <section class="section-padding bg-gradient-to-b from-slate-900 via-slate-900 to-black">
    <div class="container-max">
      <SectionHeading>Featured Projects</SectionHeading>
      
      <div class="grid md:grid-cols-2 gap-8 lg:gap-10">
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
import SectionHeading from './SectionHeading.vue'

const projects = ref([
  {
    id: 1,
    title: 'JobZ Platform',
    description: 'A platform helping young Liberians find employment opportunities. Connecting job seekers with employers and creating pathways to economic empowerment.',
    techStack: ['Vue.js', 'Node.js', 'MongoDB', 'TailwindCSS'],
    image: '/placeholder.jpg',
    status: 'In Progress',
    highlight: true,
    githubUrl: 'https://github.com',
    liveUrl: null,
  },
  {
    id: 2,
    title: 'Church Management System API',
    description: 'A comprehensive backend API for managing church operations including member records, events, donations, and administrative tasks. Built as my capstone project.',
    techStack: ['Django', 'Python', 'REST API', 'JWT Auth', 'PostgreSQL'],
    image: '/placeholder.jpg',
    status: 'In Progress',
    highlight: true,
    githubUrl: 'https://github.com',
    liveUrl: null,
  },
  {
    id: 3,
    title: 'Movie Database App',
    description: 'A sample application for browsing and searching movies. Demonstrates API integration, state management, and modern UI/UX principles.',
    techStack: ['Vue.js', 'TailwindCSS', 'TMDB API', 'JavaScript'],
    image: '/Screenshot 2025-12-11 215657.png',
    status: 'Active',
    githubUrl: 'https://github.com',
    liveUrl: 'https://example.com',
  },
  {
    id: 4,
    title: 'Music Player',
    description: 'A sleek music player application showcasing audio controls, playlist management, and responsive design. Built to explore frontend audio APIs.',
    techStack: ['Vue.js', 'TailwindCSS', 'JavaScript', 'Web Audio API'],
    image: '/placeholder.jpg',
    status: 'Active',
    githubUrl: 'https://github.com',
    liveUrl: 'https://example.com',
  },
])
</script>

