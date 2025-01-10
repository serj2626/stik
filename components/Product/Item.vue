<script>
export default {
  props: {
    product: {
      type: Object,
      required: true,
    },
  },
};
</script>
<template>
  <article class="card">
    <img class="card__img" :src="product.src" :alt="product.title" />
    <div class="card__body">
      <p class="card__title">{{ product.title }}</p>
      <div class="card__price">{{ product.price }}</div>
    </div>
  </article>
</template>

<style scoped>
.card {
  margin-bottom: 100px;
  cursor: pointer;
  transition: box-shadow 0.2s ease-in-out;

  &:hover {
    box-shadow: 5px 5px 15px 0 var(--color-gray-text);
  }
}
.card__body {
  font-size: 10px;
  line-height: 14px;
  padding-left: 15px;
  padding-bottom: 7px;
  color: var(--color-text);
}

.card__title {
  margin-top: 15px;
  margin-bottom: 10px;
  font-size: 10px;
  line-height: 14px;
}

.card__price {
  font-size: 10px;
  line-height: 14px;
}

.card__img {
  width: 100%;
}

@media screen and (max-width: 900px) {
  .card {
    margin-bottom: 32px;
    gap: 8px;
  }
}
</style>
