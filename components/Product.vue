<template>
  <div :class="$style.root">
    <img
      :class="$style.img"
      :src="require('../assets/img/image.jpg')"
      alt="Изображение товара"
      width="332"
      height="200"
    />
    <div :class="$style.info">
      <h3 :class="$style.title">Наименование товара</h3>
      <p :class="$style.description">
        Довольно-таки интересное описание товара в несколько строк.
        Довольно-таки интересное описание товара в несколько строк
      </p>
      <span :class="$style.price"> 10 000 руб. </span>
    </div>
    <button :class="$style.deleteBtn">
      <Icon />
    </button>
  </div>
</template>

<script>
import Icon from '~/assets/img/delete-icon.svg?inline';

export default {
  name: 'Product',
  components: { Icon },
};
</script>

<style lang="scss" module>
@import '~/assets/Scss/variables.scss';

.root {
  display: flex;
  position: relative;
  flex-direction: column;
  box-shadow: $shadow-primary;

  &:hover > .deleteBtn {
    display: block;
  }
}

.deleteBtn {
  display: none;
  position: absolute;
  background-repeat: no-repeat;
  background-color: $basic-pink;
  width: 32px;
  height: 32px;
  border-radius: 10px;
  border: none;
  padding: 0;
  right: -8px;
  top: -8px;

  &:hover {
    background-color: lighten($basic-pink, 5%);
  }
}

.img {
  display: block;
  width: 100%;
  background-color: gray;
}

.info {
  padding: 16px 16px 24px 16px;
}

.title {
  margin: 0;
  margin-bottom: 16px;
  font-size: 20px;
  line-height: 25px;
  font-weight: 600;
}
.description {
  margin: 0;
  margin-bottom: 32px;
}

.price {
  font-weight: 600;
  font-size: 24px;
  line-height: 30px;
}
</style>
