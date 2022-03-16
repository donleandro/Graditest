<template>
  <div>
    <h1>{{ title }}</h1>
    <span>$ {{discountPrice}}<small>{{ price }}</small></span>
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