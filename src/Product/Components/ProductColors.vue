<template>
  <div class="column">
    Color
    <div class="colors">
    <div class="color" :style="{'background-color':color}" :class="selectedColor === index? 'selected':'' " v-for="(color, index) in colors" :id="'color'+index" v-bind:key="index">
    </div>
    </div>

  </div>
</template>
<script>
export default {
  name: 'ProductColors',
  props: {
    colors: {
      type: Array,
      required: true
    },
  },
  data() {
    return {
      selectedColor: 0
    }
  },
  computed: {
    selectedColorId() {
      return this.selectedColor ? this.selectedColor.id : null
    }
  },
  methods: {
    selectColour(colour) {
      this.selectedColor = colour
    }
  },
  created() {
    // this.colours = this.product.colours
    // this.selectedColour = this.colours[0]
  }
}
</script>
<style scoped lang="scss">
.colors{
  margin-bottom: 40px;
  display: flex;
  justify-content: center;
  .selected{
    &:after{
      content: "";
      width: 30px;
      height: 30px;
      border: 2px solid #3e3e3e88;
      position: absolute;
      border-radius: 50%;
      box-sizing: border-box;
      left: -7px;
      top: -7px;
    }
  }
}
.color{
  width: 16px;
  height: 16px;
  margin: 0 10px;
  border-radius: 50%;
  cursor: pointer;
  position: relative;

}
</style>