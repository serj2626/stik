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
      <ProductItem
        v-for="(product, index) in products"
        :key="index"
        :product="product"
      />
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

@media screen and (max-width: 900px) {
  .galery__cards {
    grid-template-columns: repeat(2, 1fr);
  }
}
</style>
