<template>
  <div>
    <label v-if="textarea" :class="$style.label">
      <span :class="$style.labelText">
        <span v-if="required" :class="$style.flag"></span>
        <slot></slot>
      </span>
      <textarea
        :value="value"
        :placeholder="placeholder"
        :class="[$style.input, $style.textarea]"
        @input="updateInput"
      ></textarea>
    </label>
    <label v-else :class="$style.label">
      <span :class="$style.labelText">
        <span v-if="required" :class="$style.flag"></span>
        <slot></slot>
      </span>
      <input
        :value="value"
        :type="type"
        :placeholder="placeholder"
        :class="$style.input"
        @input="updateInput"
      />
    </label>
  </div>
</template>

<script>
export default {
  name: 'TextField',
  props: {
    // eslint-disable-next-line vue/require-default-prop
    value: {
      type: [String, Number],
    },
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

  methods: {
    updateInput(event) {
      this.$emit('input', event.target.value);
    },
  },
};
</script>

<style lang="scss" module>
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
  font-family: $font-family;
  font-size: 12px;
  line-height: 15px;
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
  min-height: 108px;
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
