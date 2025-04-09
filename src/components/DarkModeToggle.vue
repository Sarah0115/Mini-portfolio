<template>
  <button class="toggle" @click="$emit('toggle')">
    <div class="toggle__container">
      <span
        :class="['toggle__label', { 'toggle__label--dark': isDark }]"
        v-text="isDark ? 'Light Mode' : 'Dark Mode'"
      ></span>
      <img
        src="/toggle.png"
        alt="Dark Mode"
        class="toggle__icon"
      />
    </div>
  </button>
</template>

<script setup>
defineProps({
  isDark: Boolean
})

defineEmits(['toggle'])
</script>

<style lang="scss" scoped>

.toggle {
  background: none;
  border: none;
  cursor: pointer;
  font-size: 0.8rem;
  display: flex;
  justify-self: end;
  align-items: flex-end;
  flex-direction: column;
  margin: 5px 10px;

  &__container {
    display: flex;
    align-items: center;
    color: $blue;
  }

  &__label {
    transition: color 0.3s ease;

    &--dark {
      color: $white;
    }
  }

  &__icon {
    width: 35px;
    height: 35px;
    margin-left: 10px;
  }
}
</style>
