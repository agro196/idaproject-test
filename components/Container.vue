<template>
  <div class="root">
    <slot></slot>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
@import '~/assets/Scss/variables.scss';

.root {
  max-width: 1440px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;

  @media (min-width: $desktop-width) {
    padding-left: 30px;
    padding-right: 30px;
  }
}
</style>
