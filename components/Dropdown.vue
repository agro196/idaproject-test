<template>
  <div
    tabindex="0"
    aria-label="Фильтрация товаров"
    :class="{ [$style.root]: true, [$style.opened]: areOptionsVisible }"
  >
    <p :class="$style.select" @click="areOptionsVisible = !areOptionsVisible">
      {{ selected.name }}
    </p>
    <div v-if="areOptionsVisible" :class="$style.options">
      <p
        v-for="option in options"
        :key="option.value"
        :class="$style.option"
        @click="selectOption(option)"
      >
        {{ option.name }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Dropdown',
  props: {
    options: {
      type: Array,
      default() {
        return [];
      },
    },
    selected: {
      type: Object,
      default() {
        return {};
      },
    },
  },
  data() {
    return {
      areOptionsVisible: false,
    };
  },
  methods: {
    selectOption(option) {
      this.$emit('select', option);
      this.areOptionsVisible = !this.areOptionsVisible;
    },
  },
};
</script>

<style lang="scss" module>
@import '~/assets/Scss/variables.scss';

.root {
  font-size: 12px;
  line-height: 15px;
  position: relative;
  width: 120px;
  padding: 10px 16px;
  background-color: $light-grey;
  border-radius: $radius;
  box-shadow: $shadow-controls;
  cursor: pointer;

  &:hover {
    background-color: darken($light-grey, 3%);
  }

  &:active {
    background-color: darken($light-grey, 5%);
  }

  &::after {
    content: ' ';
    position: absolute;
    width: 5px;
    height: 5px;
    border-left: 1px solid $basic-grey;
    border-bottom: 1px solid $basic-grey;
    display: block;
    transform: rotate(-45deg);
    right: 16px;
    top: 14px;
    transition: transform 0.3s ease-out;
  }
}

.opened {
  &::after {
    transform: rotate(135deg);
  }
}

.select {
  margin: 0;
  color: $basic-grey;
}

.option {
  margin: 0;
  background-color: $light-grey;
  padding: 10px 16px;

  &:hover {
    background-color: $secondary-grey;
  }
}

.options {
  position: absolute;
  width: 100%;
  left: 0;
  top: 40px;
  z-index: 1;
}
</style>
