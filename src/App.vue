<template>
  <div class="app" :class="{ 'app--dark': isDark }">
    <header class="app__header">
      
      <DarkModeToggle @toggle="toggleDarkMode" :is-dark="isDark"/>
      <h1 class="app__title">Mini Portfolio Sarah</h1>
    </header>
    <main class="app__main">
      <div class="app__intro">
        I've created a portfolio of cats, at the end of the day they are more entertained that real projects that you 
        can not interact with, if you actually want to see some cats, I meant projects (or the few I could rescue),
        here <a href="https://sarahp0115.blogspot.com/"> some pictures of those</a> 
      </div>
      <section class="projects">
        <ProjectCard v-for="project in projects" :key="project.id" :project="project" @open="openModal" class="project-card"/>
      </section>
      <ProjectModal v-if="selectedProject" :project="selectedProject" @close="selectedProject = null" />
    </main>
  </div>
</template>

<script>
import projects from './data/projects.json';
import ProjectCard from './components/ProjectCard.vue';
import ProjectModal from './components/ProjectModal.vue';
import DarkModeToggle from './components/DarkModeToggle.vue';

export default {
  components: { ProjectCard, ProjectModal, DarkModeToggle },
  data() {
    return {
      projects,
      selectedProject: null,
      isDark: false
    };
  },
  methods: {
    openModal(project) {
      this.selectedProject = project;
    },
    toggleDarkMode() {
      this.isDark = !this.isDark;
    }
  }
};
</script>
