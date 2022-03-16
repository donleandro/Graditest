<template>
  <div class="column column-quantity">
    <div class="picker noselect">
      <div class="number-picker">
      <span class="number-picker__minus" @click="decrementQuantity">
        -
      </span>
        <span class="number-picker__input">
        <input v-model="quantity" :max="maxQuantity" :min="minQuantity" type="number"
               @change="updateQuantity">
      </span>

        <span class="number-picker__plus" @click="incrementQuantity">
        +
      </span>
      </div>
    </div>
    <div class="total-price">
      <span class="total-price__label">
        Total:
      </span>
      <span class="total-price__value">
        $ {{ totalPrice }}
      </span>
    </div>
  </div>
  <div class="column column-buttons">
    <div class="btn btn--secondary btn-favourite">Add to Favourite</div>
    <div class="btn btn--primary btn-cart">Add to Cart</div>

  </div>
  <div class="column column-description">
    <p class="description" v-html="description"></p>
  </div>
</template>
<script>
export default {
  name: 'ProductCta',
  props: {
    description: {
      type: String,
      required: true
    },
    price: {
      type: Number,
      required: true
    },
  },
  data() {
    return {
      quantity: 1,
      maxQuantity: 10,
      minQuantity: 1,
      totalPrice: 0
    }
  },
  mounted() {
    this.calculateTotalPrice();
  },
  methods: {
    calculateTotalPrice() {
      this.totalPrice = this.quantity * this.price;
    },
    incrementQuantity() {
      this.quantity++;
      if (this.quantity > this.maxQuantity) {
        this.quantity = this.maxQuantity;
      }
    },
    decrementQuantity() {
      this.quantity--;
      if (this.quantity <= this.minQuantity) {
        this.quantity = this.minQuantity;
      }
    },
    updateQuantity() {
      this.$emit('update-quantity', this.quantity);
    }
  },
  watch: {
    quantity() {
      this.calculateTotalPrice();
    }
  }
}
</script>
<style lang="scss" scoped>
$margin: 2%;
.column-description {
  padding: 0 !important;
}

.column-buttons {
  padding: 0 !important;
}
.column-quantity {
  padding: 0 !important;
  display: inline-flex!important;
  justify-content: space-between;
  align-items: baseline;
}

.description {
  font-size: 1.3rem;
  margin-top: 1rem;
}

.btn-favourite {
  width: calc(50% - #{$margin});
  margin-right: #{$margin};
}

.btn-cart {
  width: calc(50% - #{$margin});
  margin-left: #{$margin};
}

.number-picker {
  display: inline-flex;
  border-collapse: separate;
  border-spacing: 0;
  line-height: 0;
  width: 100px;
  flex-direction: row;
  flex-wrap: nowrap;
  padding: 6px;
  border: 1px solid grey;
  border-radius: 4px;
  margin-bottom: 16px;
  cursor: pointer;

  &__input {
    width: 100%;
    text-align: center;
    border: none;
    outline: none;
    font-size: 1.3rem;
    padding: 0;
    position: relative;
    display: inline-block;

    &::-webkit-inner-spin-button,
    &::-webkit-outer-spin-button {
      -webkit-appearance: none;
      margin: 0;
    }

    input {
      border: none;
      outline: none;
      text-align: center;
      width: 35px;
      font-size: 2rem;
    }

    input::-webkit-outer-spin-button,
    input::-webkit-inner-spin-button {
      -webkit-appearance: none;
      margin: 0;
    }

    /* Firefox */
    input[type=number] {
      -moz-appearance: textfield;
    }
  }

  &__minus {
    position: relative;
    display: inline-block;
    border-radius: 50% !important;
    border: none;
    background: white;
    width: 24px;
    height: 24px;
    font-size: 3rem;
    font-weight: 600;
    line-height: .8;
  }

  &__plus {
    position: relative;
    display: inline-block;
    border-radius: 50% !important;
    border: none;
    background: white;
    width: 24px;
    height: 24px;
    font-size: 3rem;
    font-weight: 600;
    line-height: .8;
  }
}

.icon-minus {
  position: relative;
  display: block;
  border-radius: 50% !important;
  border: none;
  background: #f2f2f2;
  width: 24px;
  height: 24px;
  line-height: 1;

  &::before {
    content: '-';
    font-size: 2rem;
    font-weight: 600;
    padding-left: 9px;
  }

}

.icon-plus {
  position: relative;
  display: block;
  border-radius: 50% !important;
  border: none;
  background: #f2f2f2;
  width: 24px;
  height: 24px;
  line-height: 1;

  &::before {
    content: '+';
    font-size: 2rem;
    font-weight: 600;
    padding-left: 9px;
  }
}
</style>