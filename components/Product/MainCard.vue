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
      <img :src="data.galerySrc" alt="Galery" />
    </div>
    <article class="product__card">
      <img :src="data.src" :alt="data.title" />
    </article>
    <div class="product__description">
      <UIButton view="accordion" />

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
          <div class="color">
            <div class="colors__item white"></div>
          </div>
          <div class="color">
            <div class="colors__item black"></div>
          </div>
          <div class="color">
            <div class="colors__item beige"></div>
          </div>
        </div>
      </div>

      <div class="buttons">
        <UIButton view="cart" />
        <UIButton view="favorite" />
      </div>

      <div class="accordion">
        <ProductAccordion
          v-for="(accordion, index) in data.accordion"
          :key="index"
          :accordion="accordion"
        />
      </div>
    </div>
  </div>
</template>

<style scoped>
/* PRODUCT */

.product {
  display: flex;
  justify-content: center;
}
.product__galery {
  margin-right: 30px;
}
.product__description {
  position: relative;
  display: flex;
  flex-direction: column;
  padding-left: 61px;
  width: 518px;
  max-height: 693px;
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
  cursor: pointer;
}

.size__count {
  text-align: center;
  margin-top: 3px;
  font-size: 10px;
  line-height: 14px;
  color: #828282;
}

.color {
  border-bottom: 1px solid transparent;
  padding: 3px;
  transition: border-color 0.2s ease-in-out;

  &:hover {
    border-color: #828282;
  }
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
  cursor: pointer;
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

@media screen and (max-width: 1000px) {
  .product {
    flex-wrap: wrap;
  }

  .product__title {
    margin-top: 31px;
  }
}

@media screen and (max-width: 618px) {
  .product__galery {
    display: none;
  }

  .product__card {
    background-color: green;
  }

  .product__description {
    width: 100%;
    padding-left: 20px;
    align-items: center;
  }
}

@media screen and (max-width: 500px) {
  .product__description {
    width: 100%;
    padding-left: 0;
  }

  .buttons {
    display: none;
  }
}
</style>
