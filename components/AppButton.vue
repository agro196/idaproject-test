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
}
.disabled {
  color: $basic-grey;
  cursor: default;
  background-color: $secondary-grey;
}

.success {
  color: $basic-white;
  background-color: $basic-green;
}
</style>
