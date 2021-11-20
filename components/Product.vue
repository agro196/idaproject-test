<template>
  <div :class="$style.root">
    <img
      :class="$style.img"
      src="#"
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
  </div>
</template>

<script>
export default {
  name: 'Product',
};
</script>

<style lang="scss" module>
.root {
  display: flex;
  flex-direction: column;
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
