<template>
  <section :class="$style.root">
    <dropdown
      :class="$style.dropdown"
      :selected="selected"
      :options="options"
      @select="optionSelect"
    />
    <h2 class="visually-hidden">Каталог товаров</h2>
    <ul :class="$style.list">
      <li :class="$style.listItem">
        <product />
      </li>
      <li :class="$style.listItem">
        <product />
      </li>
      <li :class="$style.listItem">
        <product />
      </li>
    </ul>
  </section>
</template>

<script>
import Dropdown from './Dropdown.vue';
import Product from './Product.vue';

export default {
  name: 'Catalog',
  components: { Product, Dropdown },
  data() {
    return {
      options: [
        { name: 'По умолчанию', value: 'default' },
        { name: 'По цене min', value: 'minPrice' },
        { name: 'По цене max', value: 'maxPrice' },
        { name: 'По имени', value: 'name' },
      ],

      selected: { name: 'По умолчанию', value: 'default' },
    };
  },
  methods: {
    optionSelect(option) {
      this.selected = option;
    },
  },
};
</script>

<style lang="scss" module>
@import '~/assets/Scss/variables.scss';

.root {
  @media (min-width: $tablet-width) {
    flex-grow: 1;
  }
}

.list {
  padding: 0;
  margin: 0;
  list-style: none;
  display: grid;
  gap: 16px;
  grid-template-columns: repeat(auto-fill, minmax(246px, 1fr));
}

.dropdown {
  margin-bottom: 16px;
  margin-left: auto;
}
</style>
