<script>
export default {
  props: {
    accordion: {
      type: Object,
      required: true,
    },
  },
  data() {
    return {};
  },
};
</script>
<template>
  <div class="accordion__item">
    <div class="accordion__title">{{ accordion.title }}</div>
    <div class="accordion__action">
      <img :src="accordion.btnSrc" alt="Plus" />
    </div>
  </div>
</template>

<style>
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
  color: var(--color-text);
}

.accordion__action {
  padding-right: 7px;
}

@media screen and (max-width: 500px) {
  .accordion__item {
    width: 100%;
    margin-inline: auto;
  }
}
</style>
