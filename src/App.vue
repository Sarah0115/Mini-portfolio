<template>
  <div class="app" :class="{ 'app--dark': isDark }">
    <header class="app__header">
      
      <DarkModeToggle @toggle="toggleDarkMode" :is-dark="isDark"/>
      <h1 class="app__title">Mini Portfolio Sarah</h1>
    </header>
    <main class="app__main">
      <div class="app__intro">
        I've created a portfolio of cats — because, let’s be honest, they’re way more entertaining than real projects you can't even interact with.  
        If you actually want to see some cats — I mean, *projects* (or at least the few I managed to rescue) —  
        check out <a href="https://sarahp0115.blogspot.com/">some pictures over here</a>.
    </div>
      <section class="projects">
        <ProjectCard v-for="project in projects" :key="project.id" :project="project" @open="openModal" class="project-card"/>
      </section>
      <ProjectModal v-if="selectedProject" :project="selectedProject" @close="selectedProject = null" />
    </main>
  </div>
</template>


<script setup>
import { ref } from 'vue'
import projects from '@/data/projects' 
import ProjectCard from '@/components/ProjectCard.vue'
import ProjectModal from '@/components/ProjectModal.vue'
import DarkModeToggle from '@/components/DarkModeToggle.vue'

const selectedProject = ref(null)
const isDark = ref(false)


function openModal(project) {
  selectedProject.value = project
}

function toggleDarkMode() {
  isDark.value = !isDark.value
}
</script>



