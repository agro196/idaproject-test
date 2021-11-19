<template>
  <div>
    <label v-if="textarea" class="label">
      <span class="labelText">
        <span v-if="required" class="flag"></span>
        <slot></slot>
      </span>
      <textarea :placeholder="placeholder" class="input textarea"></textarea>
    </label>
    <label v-else class="label">
      <span class="labelText">
        <span v-if="required" class="flag"></span>
        <slot></slot>
      </span>
      <input :placeholder="placeholder" :type="type" class="input" />
    </label>
  </div>
</template>

<script>
export default {
  props: {
    textarea: {
      type: Boolean,
      default: false,
    },
    placeholder: {
      type: String,
      default: '',
    },
    type: {
      type: String,
      default: 'text',
    },
    required: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style lang="scss" scoped>
@import '~/assets/Scss/variables.scss';

.label {
  display: flex;
  flex-direction: column;
}
.labelText {
  position: relative;
  align-self: flex-start;
  margin-bottom: 4px;
  font-size: 10px;
  line-height: 12px;
  color: $secondary-black;
}

.input {
  padding: 10px 16px;
  border: none;
  border-radius: $radius;
  box-shadow: $shadow-controls;

  &::placeholder {
    font-family: $font-family;
    font-size: 12px;
    color: $basic-grey;
  }
}

.textarea {
  resize: none;
}

.flag {
  position: absolute;
  border-radius: $radius;
  right: -6px;
  width: 4px;
  height: 4px;
  background-color: $basic-pink;
}
</style>
