<template>
    <div class="project" @click="$emit('open', project)">
      <img :src="project.image" alt="" class="project__image" />
      <h2 class="project__title">{{ project.title }}</h2>
      <p class="project__description">{{ project.description }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: ['project']
  };
  </script>
  
  <style scoped lang="scss">
  .project {
    &__image {
      width: 100%;
      border-radius: 0.5rem;
    }
    &__title {
      font-size: 1.25rem;
      margin-top: 0.5rem;
    }
    &__description {
      font-size: 1rem;
      margin: 20px 0;
    }
  }
  </style>
  