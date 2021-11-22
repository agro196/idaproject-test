<template>
  <main>
    <Container :class="$style.container">
      <h1 class="visually-hidden">Главная страница приложения</h1>
      <AppForm :class="$style.form" />
      <Catalog />
    </Container>
  </main>
</template>

<script>
export default {};
</script>

<style lang="scss" module>
@import '~/assets/Scss/variables.scss';

.container {
  padding-top: 32px;
  padding-bottom: 32px;
  display: flex;
  flex-direction: column;
  gap: 16px;

  @media (min-width: $tablet-width) {
    flex-direction: row;
  }
}

.form {
  @media (min-width: $tablet-width) {
    min-width: 332px;
    align-self: flex-start;
  }
}
</style>
