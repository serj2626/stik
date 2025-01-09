<script>
export default {
  props: {
    view: {
      type: String,
      required: true,
    },
  }
};
</script>
<template>
  <button v-if="view === 'cart'" class="btn__tocart">
    <div class="btn__title">Добавить в корзину</div>
  </button>
  <button v-else class="btn__favorite">
    <img src="~assets/images/Stroke.svg" alt="favorite" />
  </button>
</template>

<style scoped>
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
</style>
