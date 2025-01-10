<script>
import { mainCard } from "~/assets/data/card.data";
export default {
  data() {
    return {
      data: mainCard,
      color: "белый",
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
          <div
            v-for="(size, index) in data.sizes"
            :key="index"
            :class="size.class"
          >
            <div class="size__item">{{ size.title }}</div>
            <div class="size__count">{{ size.count ? size.count : "" }}</div>
          </div>
        </div>
      </div>

      <div class="colors">
        <p class="colors__title">Цвет: {{ color }}</p>
        <div class="colors__list">
          <div
            @mouseover="color = 'белый'"
            class="color"
            :class="{ colorActive: color === 'белый' }"
          >
            <div class="colors__item white"></div>
          </div>
          <div
            @mouseover="color = 'чёрный'"
            class="color"
            :class="{ colorActive: color === 'чёрный' }"
          >
            <div class="colors__item black"></div>
          </div>
          <div
            @mouseover="color = 'бежевый'"
            class="color"
            :class="{ colorActive: color === 'бежевый' }"
          >
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
  color: var(--color-black);
}

.product__price {
  margin-bottom: 28px;
  color: var(--color-black);
}
.accordion {
  width: 100%;
}
.product__price {
  font-size: 12px;
  line-height: 16px;
}

.noActive .size__item {
  border: 1px solid var(--color-gray);
  color: var(--color-gray);
}

.size__title {
  font-size: 10px;
  line-height: 14px;
  margin-top: 28px;
  margin-bottom: 8px;
  color: var(--color-gray-text);
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

  color: var(--color-text);
  width: 65px;
  height: 31px;
  text-transform: uppercase;
  font-size: 10px;
  line-height: 14px;

  border: 1px solid var(--color-text);
  cursor: pointer;
}

.size__count {
  text-align: center;
  margin-top: 3px;
  font-size: 10px;
  line-height: 14px;
  color: var(--color-gray);
}

.color {
  border-bottom: 1px solid transparent;
  padding: 3px;
  transition: border-color var(--transition-delay) var(--transition-cubic);
  /* transition: border-color 0.2s ease-in-out; */
}

.colorActive {
  border-color: var(--color-gray-text);
}

.colors__title {
  font-size: 10px;
  line-height: 14px;
  color: var(--color-gray-text);
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
  border: 1px solid var(--color-gray);
  cursor: pointer;
}

.white {
  background-color: var(--color-white);
}

.black {
  background-color: var(--color-black);
}

.beige {
  background-color: var(--color-beige);
}

.buttons {
  display: flex;
  align-items: center;
  gap: 10px;
  margin-bottom: 40px;
}

/* .accordion {
  width: 100%;
} */

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

  .product__description {
    width: 100%;
    margin-inline: 16px;
    align-items: start;
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

  .product__price {
    margin-bottom: 31px;
  }
}
</style>
