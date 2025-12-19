<template>
  <section id="experience" class="section-padding bg-black">
    <div class="container-max">
      <h2 class="text-4xl md:text-5xl font-bold text-center mb-16 bg-gradient-to-r from-blue-400 to-indigo-400 bg-clip-text text-transparent">
        Experience & Volunteering
      </h2>
      
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
        <a 
          href="#contact" 
          @click.prevent="scrollToContact"
          class="inline-block px-8 py-3 bg-gradient-to-r from-blue-600 to-indigo-600 text-white rounded-lg font-semibold soft-shadow-lg hover:shadow-xl transform hover:-translate-y-1 transition-all duration-200"
        >
          Let's Connect
        </a>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'
import ExperienceItem from './ExperienceItem.vue'

const experienceItems = ref([
  {
    id: 1,
    title: 'Founder & Developer',
    organization: 'JobZ Platform',
    type: 'Entrepreneurship',
    period: '2025 - Present',
    description: 'Leading the development and growth of JobZ, a platform dedicated to connecting young Liberians with employment opportunities. Responsible for full-stack development, product strategy, and community engagement.',
    highlights: [
      'Building scalable platform architecture',
      'Engaging with local communities and employers',
      'Creating impact in youth employment',
    ],
  },
  {
    id: 2,
    title: 'Backend Capstone Project',
    organization: 'Church Management System API',
    type: 'Academic Project',
    period: '2024',
    description: 'Developing a comprehensive REST API for church management systems. This capstone project demonstrates advanced Django skills, API design, authentication, and database optimization.',
    highlights: [
      'RESTful API design and implementation',
      'JWT authentication and authorization',
      'Database schema design and optimization',
    ],
  
  },
  {
    id: 3,
    title: 'Student Leadership',
    organization: 'Forensic Science Programs',
    type: 'Leadership',
    period: 'Ongoing',
    description: 'Actively participating in student organizations and seeking leadership roles that allow me to contribute to my academic community while developing soft skills and networking.',
    highlights: [
      'Team collaboration and communication',
      'Event organization and management',
      'Peer mentorship and support',
    ],
    
  },
  {
    id: 4,
    title: 'Volunteer & Community Service',
    organization: 'Various Initiatives',
    type: 'Volunteering',
    period: 'Ongoing',
    description: 'Committed to giving back to my community through technology education, mentorship programs, and supporting initiatives that align with my values of empowerment and progress.',
    highlights: [
      'Tech mentorship for beginners',
      'Community outreach programs',
      'Promoting STEM education',
    ],
  },
])

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

