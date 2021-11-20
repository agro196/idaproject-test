<template>
  <section :class="$style.root">
    <h2 class="visually-hidden">Каталог товаров</h2>
    <ul :class="$style.list">
      <li :class="$style.listItem">
        <product />
      </li>
    </ul>
  </section>
</template>

<script>
import Product from './Product.vue';

export default {
  name: 'Catalog',
  components: { Product },
};
</script>

<style lang="scss" module>
.list {
  padding: 0;
  margin: 0;
  list-style: none;
}
</style>
