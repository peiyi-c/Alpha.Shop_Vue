<template>
  <div class="cart">
    <div class="cart-title">購物籃</div>
    <div class="cart-items">
      <div class="cart-item" v-for="product in products" :key="product.id">
        <div class="item-image">
          <img :src="product.image" alt="" />
        </div>
        <div class="item-name">{{ product.name }}</div>
        <div class="item-counter">
          <div class="item-minus" @click="minusNumber(product)">-</div>
          <span class="item-number">{{ product.number }}</span>
          <div class="item-plus" @click="addNumber(product)">+</div>
        </div>
        <div class="item-price">${{ product.price | comma }}</div>
      </div>
    </div>
    <div class="cart-checkout d-flex flex-column align-items-center">
      <div class="checkout checkout-shipping d-flex justify-content-between">
        <div class="checkout-shipping-title">運費</div>
        <div class="checkout-shippingfee">
          {{ shippingFee | ifFree }}
        </div>
      </div>
      <div class="checkout checkout-sum d-flex justify-content-between">
        <div class="checkout-sum-title">小計</div>
        <div class="checkout-sum-end">${{ sumEndWithShippingFee | comma }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CheckoutCart",
  props: {
    initialProducts: {
      type: Array,
      require: true,
    },
    shippingFee: {
      type: Number,
      require: true,
    },
  },
  data() {
    return {
      products: this.initialProducts,
      sumEnd: 5298,
    };
  },
  methods: {
    addNumber(product) {
      product.number++;
      this.sumEnd += product.price;
    },
    minusNumber(product) {
      if (product.number > 1) {
        product.number--;
        this.sumEnd -= product.price;
      } else {
        return (product.number = 1);
      }
    },
  },
  computed: {
    sumEndWithShippingFee() {
      return this.sumEnd + this.shippingFee;
    },
  },
  filters: {
    ifFree(n) {
      return n === 0 ? "免費" : "$ " + n;
    },
    comma(n) {
      return (n = new Intl.NumberFormat("en-IN").format(n));
    },
  },
};
</script>


<style lang="scss" scoped>
@import "../style/reset.scss";
@import "../style/mixin.scss";
@import "../style/each.scss";
@import "../style/panel.scss";
</style>