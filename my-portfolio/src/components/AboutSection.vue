<template>
  <section class="section-padding bg-slate-900">
    <div class="container-max">
      <SectionHeading>About Me</SectionHeading>
      
      <div class="grid md:grid-cols-2 gap-12 items-start">
        <div class="space-y-6">
          <div class="soft-shadow-lg rounded-2xl p-8 bg-slate-800 border border-slate-700">
            <h3 class="text-2xl font-bold text-slate-100 mb-4">My Academic Journey</h3>
            <p class="text-slate-300 leading-relaxed">
              I'm a dedicated Forensic Science student pursuing my degree across two universities in Liberia. 
              My academic path is driven by a passion for justice and a curiosity about how technology can 
              revolutionize the field of digital forensics. Balancing studies at two institutions has taught 
              me discipline, time management, and the value of diverse perspectives.
            </p>
          </div>
          
          <div class="soft-shadow-lg rounded-2xl p-8 bg-slate-800 border border-slate-700">
            <h3 class="text-2xl font-bold text-slate-100 mb-4">Finding My Purpose</h3>
            <p class="text-slate-300 leading-relaxed">
              My journey into technology wasn't linear. As a Forensic Science student, I discovered that 
              digital evidence and cyber forensics are becoming increasingly crucial in modern investigations. 
              This realization sparked my interest in frontend development, APIs, and building robust systems 
              that can handle complex data processing—skills directly applicable to digital forensics.
            </p>
          </div>
        </div>
        
        <div class="space-y-6">
          <div class="soft-shadow-lg rounded-2xl p-8 bg-slate-800 border border-slate-700">
            <h3 class="text-2xl font-bold text-slate-100 mb-4">Focus Areas</h3>
            <ul class="space-y-4 text-slate-300">
              <li class="flex items-start">
                <div>
                  <strong class="text-slate-100">Digital Forensics:</strong> Exploring how technology intersects 
                  with criminal investigations and evidence collection.
                </div>
              </li>
              <li class="flex items-start">
                <div>
                  <strong class="text-slate-100">Frontend Development:</strong> Building scalable User Interface and 
                  systems using VUE, Tailwindcss, and modern web technologies.
                </div>
              </li>
              <li class="flex items-start">
                <div>
                  <strong class="text-slate-100">TinyML & AI:</strong> Learning how machine learning on 
                  edge devices can solve real-world problems.
                </div>
              </li>
            </ul>
          </div>
          
          <div class="soft-shadow-lg rounded-2xl p-8 bg-slate-800 border border-slate-700">
            <h3 class="text-2xl font-bold text-slate-100 mb-4">Beyond the Code</h3>
            <p class="text-slate-300 leading-relaxed">
              When I'm not coding or studying, I'm working on <strong class="text-slate-100">JobZ</strong>—a platform I founded to 
              help young Liberians find meaningful employment opportunities. This project combines my passion 
              for technology with my desire to create positive social impact in my community.
            </p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import SectionHeading from './SectionHeading.vue'
</script>

