<template>
  <div>
    <h1>{{ title }}</h1>
    <div class="product-price">
      <span>
        <span class="price">$ {{ discountPrice }}</span>
        <span class="price__original">{{ price }}</span>
      </span>
    </div>
  </div>
</template>
<script>
export default {
  name: 'ProductTitle',
  props: {
    title: {
      type: String,
      required: true
    },
    price: {
      type: Number,
      required: true
    },
    discountPrice: {
      type: Number,
      required: true
    }
  }
}
</script>
<style lang="scss" scoped>
.product-price {
  font-size: 22px;
  line-height: 22px;
  font-weight: 700;
}

.price {
  font-size: 2.4rem;
  font-weight: bold;
  color: var(--color-primary);
  &__original {
    color: var(--color-secondary);
    font-size: 1.8rem;
    margin-left: 10px;
    font-weight: 500;
    text-decoration: line-through;
  }
}

</style>