<script>
export default {
  props: {
    view: {
      type: String,
      required: true,
    },
  },
};
</script>
<template>
  <button v-if="view === 'cart'" class="btn__tocart">
    <div class="btn__title">Добавить в корзину</div>
  </button>
  <button v-else-if="view === 'favorite'" class="btn__favorite">
    <img src="~assets/images/Stroke.svg" alt="favorite" />
  </button>

  <button v-else class="btn__media">
    <img src="~assets/images/Stroke.svg" alt="favorite-media" />
  </button>
</template>

<style scoped>
.btn__title {
  font-size: 11px;
  line-height: 15px;
  width: 257px;
  height: 14px;
  color: var(--color-white);
  text-transform: uppercase;
  text-align: center;
}

.btn__tocart {
  padding: 15px 25px;
  background-color: var(--color-black);
  border: 1px solid currentColor;
}

.btn__favorite {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: var(--color-white);

  width: 44px;
  height: 44px;

  border: var(--border-black);
}

.btn__media {
  display: none;
  padding: 10px;
  border: none;
  background-color: var(--color-white);
  position: absolute;
  top: 13px;
  right: 0;
}

@media screen and (max-width: 500px) {
  .btn__media {
    display: block;
    position: absolute;
    top: 13px;
    right: 0;
  }
}
</style>
