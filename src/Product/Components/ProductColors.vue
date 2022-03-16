<template>
  <div class="container row color-wrapper">
    <span class="column column-20">
    Color
    </span>
    <div class="column column-80">
      <div class="colors">
        <div v-for="(color, index) in colors" :id="'color'+index" v-bind:key="index"
             :class="selectedColor === index? 'selected':'' " :style="{'background-color':color}" class="color">
        </div>
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
<style lang="scss" scoped>
.color-wrapper {
  margin-top: 28px;
  margin-bottom: 10px;
}

.title_color {
  display: inline-block;
}

.colors {
  display: flex;
  margin-left: 10px;

  .selected {
    &:after {
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

.color {
  width: 16px;
  height: 16px;
  margin: 0 10px;
  border-radius: 50%;
  cursor: pointer;
  position: relative;

}
</style>