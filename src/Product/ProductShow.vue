<template>
  <div v-if="!loading" class="container row wrapper">
    <div class="column column--left">
      <ProductCarousel :images="product.images" :featured="product.featured_image"/>
    </div>
    <div class="column column--right">
      <ProductTitle :title="product.title" :discountPrice="product.price" :price="product.price_max" />
      <hr />
      <ProductColors :colors="product.options[0].values" />
      <hr />
      <ProductSizes :sizes="product.options[1].values" />
      <hr />
      <ProductCta :description="product.description" :price="product.price"></ProductCta>
    </div>
  </div>
</template>
<script>
import axios from 'axios';
import ProductCarousel from "../Product/Components/ProductCarousel.vue";
import ProductTitle from "../Product/Components/ProductTitle.vue";
import ProductColors from "../Product/Components/ProductColors.vue";
import ProductSizes from "../Product/Components/ProductSizes.vue";
import ProductCta from "../Product/Components/ProductCta.vue";

export default {
  name: "ProductShow",
  components: {ProductCarousel, ProductTitle, ProductColors, ProductCta,ProductSizes
  },
  data(){
    return{
      product: {},
      loading: true,
    }
  },
  mounted() {
    this.getData();
  },
  methods: {
    //fetch data with axios from https://graditest-store.myshopify.com/products/free-trainer-3-mmw.js
    async getData() {
      await axios.get('https://graditest-store.myshopify.com/products/free-trainer-3-mmw.js')
      .then(response => {
        this.product = response.data;
        console.log(this.product);
      })
      .catch(error => {
        console.log(error);
      })
    .finally(() => this.loading = false);
    }
  }
}
</script>
<style lang="scss">
.col{
  min-height: 1px;
  padding-left: 15px;
  padding-right: 15px;
  position: relative;
  width: 100%;
  &--left{
    flex: 0 0 60%;
    max-width: 60%;
  }
  &--right{
    flex: 0 0 40%;
    max-width: 40%;
  }
}
.row{
  display: flex;
  flex-wrap: wrap;
  margin-left: -15px;
  margin-right: -15px;
  &_max{
    max-width: 1100px;
    margin: auto auto;
  }
}
@media screen and (max-width: 768px){
  .column{
    &--left{
      flex: 0 0 100%!important;
      max-width: 100%!important;
    }
    &--right{
      flex: 0 0 100%!important;
      max-width: 100%!important;
    }
  }
}
@media (min-width: var(--phone)) and (max-width: var(--tablet)){

}

</style>