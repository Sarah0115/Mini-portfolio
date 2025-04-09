<template>
  <div class="project" @click="$emit('open', project)">
    <img :src="project.image" :alt="project.title" class="project__image" />
    <h2 class="project__title">{{ project.title }}</h2>
    <p class="project__description">{{ project.description }}</p>
  </div>
</template>

<script setup>
defineProps({
  project: Object,
});

defineEmits(["open"]);
</script>

<style scoped lang="scss">

.project {
  cursor: pointer;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  padding: 1rem;
  border-radius: 1rem;
  background-color: $card-bg;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);

  &:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
  }

  &__image {
    width: 100%;
    border-radius: 0.5rem;
    object-fit: cover;
    margin-bottom: 0.5rem;
  }

  &__title {
    font-size: 1.25rem;
    font-weight: 600;
    margin: 0.5rem 0;
    color: $text;
  }

  &__description {
    font-size: 1rem;
    line-height: 1.5;
    color: $text;
    margin-bottom: 0;
  }
}
</style>
