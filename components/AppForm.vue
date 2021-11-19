<template>
  <form class="root">
    <text-field placeholder="Введите наименование товара" required type="text"
      >Привет</text-field
    >
  </form>
</template>

<script>
import TextField from './TextField.vue';

export default {
  name: 'AppForm',
  components: {
    TextField,
  },
};
</script>

<style lang="scss" scoped>
@import '~/assets/Scss/variables.scss';

.root {
  background-color: $pearl;
  box-shadow: $shadow-primary;
}
</style>
