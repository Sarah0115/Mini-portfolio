
<template>
  <div class="modal" @click.self="$emit('close')">
    <div class="modal__content">
      <h2 class="modal__content-title">{{ project.title }}</h2>
      <img :src="project.image" alt="" />
      <p class="modal__content-description">{{ project.description }}</p>
      <div class="modal__footer">
        <a :href="project.link" target="_blank">Visit Project</a>
        <button @click="$emit('close')">Close</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['project']
};
</script>

<style scoped lang="scss">
.modal {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0,0,0,0.6);
  display: flex;
  align-items: center;
  justify-content: center;

  &__content {
    background: $bg;
    color: $text;
    padding: 2rem;
    border-radius: 1rem;
    max-width: 600px;
    width: 100%;
  }
  &__content-title{
      margin: 20px 0;
    }
  &__content-description{
      margin: 20px 0;
    }
  &__footer{
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
}
/* Responsive Extras */
@media (max-width: 600px) {
  .modal__content{
    margin: 20px;
  }
}


</style>
