<template>
  <div class="modal" @click.self="$emit('close')">
    <div class="modal__content">
      <h2 class="modal__title">{{ project.title }}</h2>
      <img :src="project.image" :alt="project.title" class="modal__image" />
      <p class="modal__description">{{ project.description }}</p>
      <div class="modal__footer">
        <a
          :href="project.link"
          target="_blank"
          rel="noopener noreferrer"
          class="modal__link"
        >
          Visit Project
        </a>
        <button class="modal__close-button" @click="$emit('close')">Close</button>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  project: Object
})

defineEmits(['close'])
</script>

<style scoped lang="scss">

.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.6);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;

  &__content {
    background: $bg;
    color: $text;
    padding: 2rem;
    border-radius: 1rem;
    max-width: 600px;
    width: 100%;
    box-shadow: 0 10px 40px rgba(0, 0, 0, 0.2);
    animation: fadeIn 0.3s ease;
  }

  &__title {
    font-size: 1.5rem;
    margin-bottom: 1rem;
  }

  &__image {
    width: 100%;
    border-radius: 0.5rem;
    margin-bottom: 1rem;
  }

  &__description {
    font-size: 1rem;
    margin-bottom: 1.5rem;
    line-height: 1.6;
  }

  &__footer {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  &__link {
    text-decoration: none;
    background-color: $blue;
    color: $white;
    padding: 0.5rem 1rem;
    border-radius: 8px;
    font-weight: 500;
    transition: background-color 0.3s ease;
  }

  &__close-button {
    background: none;
    border: 1px solid $text;
    padding: 0.5rem 1rem;
    border-radius: 8px;
    cursor: pointer;
    color: $text;

    &:hover {
      background-color: rgba(255, 255, 255, 0.1);
    }
  }
}

/* Responsive */
@media (max-width: 600px) {
  .modal__content {
    margin: 1rem;
    padding: 1.5rem;
  }
}

/* Animation */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: scale(0.97);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}
</style>
