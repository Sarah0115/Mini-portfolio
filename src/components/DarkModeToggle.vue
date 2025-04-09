
<template>
  <button class="toggle" @click="$emit('toggle')">
    <div class="toggle__container">
      <span :class="isDark ? 'dark' : ''" v-text="isDark ? 'Light Mode' : 'Dark Mode'"></span>
      <img src="/toggle.png" alt="Dark Mode" class="toggle__container-img">
  </div>
    
  </button>
</template>
<script>
export default {
  props: ['project', 'isDark']
};
</script>

<style lang="scss" scoped>

.toggle {
  background: none;
  border: none;
  font-size: 0.8rem;
  cursor: pointer;
  display: flex;
  justify-self: end;
  align-items: end;
  flex-direction: column;
  margin: 5px 10px;
  &__container{
    display: flex;
    align-items: center;
    color: $blue;
    .dark{
      color: $white;
    }
  }
  &__container-img{
    width: 35px;
    height: 35px;
    margin: 0 10px;
  }
}
</style>
