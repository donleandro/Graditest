<template>
  <div class="container sizes-wrapper row">
    <span class="title_sizes column column-20">
      Talla:
    </span>
    <div class="sizes-container column column-80">
      <div v-for="(size,index) in sizes" class="size-item" :key="index" :class="{'size-item__selected': selectedSize.includes(size)}">
        <span class="size-item-text">{{ size }}</span>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'ProductSizes',
  props: {
    sizes: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      selectedSize: ['9']
    }
  },
  methods: {
    selectSize(size) {
      this.selectedSize = size
    }
  }
}
</script>
<style scoped lang="scss">
.size{
  &-item{
    cursor: pointer;
    display: inline-grid;
    width: 40px;
    height: 40px;
    border: 1px solid #d5d5d5;
    /* vertical-align: middle; */
    color: #d5d5d5;
    margin: 7px;
    &-text{
      text-align: center;
      position: relative;
      top: 50%;
      -webkit-transform: translateY(-50%);
      -ms-transform: translateY(-50%);
      transform: translateY(-35%);
    }
&__selected{
  border: 1px solid black;
  color: black;
}
}
}
</style>