<script>
import { mainCard } from "~/assets/data/card.data";
export default {
  data() {
    return {
      data: mainCard,
    };
  },
};
</script>
<template>
  <div class="product">
    <div class="product__galery">
      <img :src="data.galerySrc" alt="" />
    </div>
    <article class="product__card">
      <img :src="data.src" alt="" />
    </article>
    <div class="product__description">
      <p class="product__title">{{ data.title }}</p>
      <span class="product__price">{{ data.price }}</span>

      <div class="size">
        <p class="size__title">Размеры</p>
        <div class="size__list">
          <div class="size" v-for="size in data.sizes">
            <div class="size__item">{{ size.title }}</div>
            <div class="size__count">{{ size.count ? size.count : "" }}</div>
          </div>
        </div>
      </div>

      <div class="colors">
        <p class="colors__title">Цвет: белый</p>
        <div class="colors__list">
          <div class="colors__item white"></div>
          <div class="colors__item black"></div>
          <div class="colors__item beige"></div>
        </div>
      </div>

      <div class="buttons">
        <button class="btn__tocart">
          <div class="btn__title">Добавить в корзину</div>
        </button>
        <button class="btn__favorite">
          <img src="assets/images/Stroke.svg" alt="" />
        </button>
      </div>

      <div class="accordion">
        <ProductAccordion v-for="accordion in data.accordion" :accordion="accordion" />
        <!-- <div class="accordion__item">
          <div class="accordion__title">Описание</div>
          <div class="accordion__action">
            <img src="assets/images/plus.svg" alt="" />
          </div>
        </div>
        <div class="accordion__item">
          <div class="accordion__title">Состав и Уход</div>
          <div class="accordion__action">
            <img src="assets/images/plus.svg" alt="" />
          </div>
        </div> -->
      </div>
    </div>
  </div>
</template>

<style scoped>
/* PRODUCT */

.product {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.product__galery {
  margin-right: 30px;
}
.product__description {
  padding-left: 61px;
  width: 518px;
  height: 693px;
}

.product__title {
  margin-bottom: 11px;
}

.product__price {
  margin-bottom: 28px;
}

.product__title,
.product__price {
  font-size: 12px;
  line-height: 16px;
}

.size__title {
  font-size: 10px;
  line-height: 14px;
  margin-top: 28px;
  margin-bottom: 8px;
}

.size__list {
  display: flex;
  gap: 14px;
  margin-bottom: 36px;
}

.size__item {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 65px;
  height: 31px;
  text-transform: uppercase;
  font-size: 10px;
  line-height: 14px;
  border: 1px solid black;
}

.size__count {
  text-align: center;
  margin-top: 3px;
  font-size: 10px;
  line-height: 14px;
  color: #828282;
}

.colors__title {
  font-size: 10px;
  line-height: 14px;
  color: #4f4f4f;
  margin-bottom: 3px;
}

.colors__list {
  display: flex;
  gap: 16px;
  margin-bottom: 40px;
}

.colors__item {
  width: 28px;
  height: 27px;
  border: 1px solid #bdbdbd;
}

.white {
  background-color: #ffffff;
}

.black {
  background-color: #000000;
}

.beige {
  background-color: #f9f1dc;
}

.buttons {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 40px;
}

.btn__title {
  font-size: 11px;
  line-height: 15px;
  width: 257px;
  height: 14px;
  color: white;
  text-transform: uppercase;
  text-align: center;
}

.btn__tocart {
  padding: 15px 25px;
  background-color: #000000;
  border: 1px solid currentColor;
}

.btn__favorite {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #fff;

  width: 44px;
  height: 44px;

  border: 1px solid black;
}

.accordion__item {
  display: flex;
  align-items: center;
  justify-content: space-between;
  width: 360px;
  padding-block: 15px;

  border-block: 1px solid #e0e0e0;
}

.accordion__title {
  text-transform: uppercase;
  font-size: 10px;
  line-height: 14px;
  color: #333333;
}

.accordion__action {
  padding-right: 7px;
}
</style>
