<template>
  <button
    :class="{
      [$style.btn]: true,
      [$style.disabled]: disabled,
      [$style.success]: success,
    }"
    :type="type"
    @click="click"
  >
    <slot />
  </button>
</template>

<script>
export default {
  name: 'AppButton',
  props: {
    type: {
      type: String,
      default: 'text',
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    success: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    click() {
      this.$emit('click');
    },
  },
};
</script>

<style lang="scss" module>
@import '~/assets/Scss/variables.scss';

.btn {
  padding: 10px;
  font-family: $font-family;
  font-size: 12px;
  line-height: 15px;
  border: none;
  background-color: $basic-blue;
  color: $basic-white;
  border-radius: $radius-button;
  transition-property: background-color;
  transition-duration: 0.3s;

  &:hover {
    background-color: lighten($basic-blue, 5%);
  }

  &:active {
    background-color: darken($basic-blue, 5%);
  }
}
.disabled {
  color: $basic-grey;
  cursor: default;
  background-color: $secondary-grey;
  pointer-events: none;
}

.success {
  color: $basic-white;
  background-color: $basic-green;

  &:hover {
    background-color: lighten($basic-green, 5%);
  }

  &:active {
    background-color: darken($basic-green, 5%);
  }
}
</style>
