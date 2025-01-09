<script>
import { productsData } from "~/assets/data/products.data";
export default {
  data() {
    return {
      products: productsData,
    };
  },
};
</script>
<template>
  <div class="container galery">
    <p class="galery__title">Похожие товары</p>
    <div class="galery__cards">
      <!-- <div class="card">
        <img
          class="card__img"
          src="assets/images/similar_products/Image_1.jpg"
          alt=""
        />
        <div class="card__body">
          <p class="card__title">ПЛАТЬЕ С V-ОБРАЗНЫМ ВЫРЕЗОМ, БЕЛЫЙ</p>
          <div class="card__price">14 900 RUB</div>
        </div>
      </div>
      <div class="card">
        <img
          class="card__img"
          src="assets/images/similar_products/Image_2.jpg"
          alt=""
        />
        <div class="card__body">
          <p class="card__title">ЖАКЕТ ДВУБОРТНЫЙ, СЕРО-ГОЛУБОЙ</p>
          <div class="card__price">8900 RUB</div>
        </div>
      </div>
      <div class="card">
        <img
          class="card__img"
          src="assets/images/similar_products/Image_3.jpg"
          alt=""
        />
        <div class="card__body">
          <p class="card__title">ПЛАТЬЕ МАКСИ С ЯРУСАМИ, БЕЛЫЙ</p>
          <div class="card__price">10 500 RUB</div>
        </div>
      </div>
      <div class="card">
        <img
          class="card__img"
          src="assets/images/similar_products/Image_4.jpg"
          alt=""
        />
        <div class="card__body">
          <p class="card__title">КОМБИНЕЗОН СО СТОЙКОЙ, ЧёРНЫЙ</p>
          <div class="card__price">9500 RUB</div>
        </div>
      </div> -->

      <div class="card" v-for="product in products">
        <img class="card__img" :src="product.src" :alt="product.title" />
        <div class="card__body">
          <p class="card__title">{{ product.title }}</p>
          <div class="card__price">{{ product.price }}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<style>
.galery {
  margin-top: 42px;
}
.galery__title {
  text-transform: uppercase;
  font-size: 12px;
  color: #333333;
  margin-bottom: 31px;
}

.galery__cards {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 9px;
}

.card {
  margin-bottom: 100px;
  cursor: pointer;
  transition: box-shadow 0.2s ease-in-out;

  &:hover {
    box-shadow: 10px 10px 5px 0 #0000005a;
  }
}
.card__body {
  font-size: 10px;
  line-height: 14px;
  padding-left: 15px;
  padding-bottom: 7px;
}

.card__title {
  margin-top: 15px;
  margin-bottom: 10px;
}
</style>
