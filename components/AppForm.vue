<template>
  <section :class="$style.root">
    <form :class="$style.form">
      <h2 :class="$style.title">Добавление товара</h2>
      <text-field
        v-model="data.name"
        :class="$style.field"
        placeholder="Введите наименование товара"
        required
        >Наименование товара
      </text-field>
      <text-field
        v-model="data.description"
        :class="$style.field"
        placeholder="Введите описание товара"
        textarea
        >Описание товара
      </text-field>
      <text-field
        v-model="data.imgRef"
        :class="$style.field"
        placeholder="Введите ссылку"
        required
        >Ссылка на изображение товара
      </text-field>
      <text-field
        v-model="data.price"
        :class="$style.field"
        placeholder="Введите цену"
        required
        >Цена товара
      </text-field>
      <app-button
        :class="$style.button"
        type="button"
        :disabled="true"
        @click="clickBtn"
        >Добавить товар</app-button
      >
    </form>
  </section>
</template>

<script>
import TextField from './TextField.vue';
import AppButton from './AppButton.vue';

export default {
  name: 'AppForm',
  components: {
    TextField,
    AppButton,
  },
  data() {
    return {
      data: {
        name: '',
        description: '',
        imgRef: '',
        price: '',
      },
    };
  },
  methods: {
    clickBtn() {},
  },
};
</script>

<style lang="scss" module>
@import '~/assets/Scss/variables.scss';

.root {
  background-color: $pearl;
  box-shadow: $shadow-primary;
}

.form {
  padding: 24px;
}

.field:not(:last-of-type) {
  margin-bottom: 16px;
}

.button {
  margin-top: 24px;
  width: 100%;
}

.title {
  margin: 0;
  margin-bottom: 16px;
  font-size: 28px;
  line-height: 25px;
  font-weight: 600;
}
</style>
