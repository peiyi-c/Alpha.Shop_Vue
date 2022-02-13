<template>
  <section class="container panel d-flex flex-column">
    <!---stepper--->
    <Stepper :step="step" />
    <!---form--->
    <div class="panel-form">
      <div class="form-content">
        <FormStep1 v-show="step === 1" />
        <FormStep2
          @shippingCostSelected="handleShippingFee"
          v-show="step === 2"
        />
        <FormStep3 v-show="step === 3" />
      </div>
    </div>
    <!---cart--->
    <div class="panel-cart">
      <CheckoutCart :initial-products="products" :shipping-fee="shippingFee" />
    </div>
    <!---button--->
    <Buttons
      :initial-step="step"
      @button-back-clicked="buttonBackClicked"
      @button-next-clicked="buttonNextClicked"
    />
  </section>
</template>

<script>
import Stepper from "./../components/Stepper";
import FormStep1 from "./../components/FormStep1";
import FormStep2 from "./../components/FormStep2";
import FormStep3 from "./../components/FormStep3";
import CheckoutCart from "./../components/CheckoutCart";
import Buttons from "./../components/Buttons";

const DummyData = {
  products: [
    {
      id: 1,
      name: "破壞補丁修身牛仔褲",
      price: 3999,
      number: 1,
      image: "https://i.imgur.com/RqUqDdu.png",
    },
    {
      id: 2,
      name: "刷色直筒牛仔褲",
      price: 1999,
      number: 1,
      image: "https://i.imgur.com/sBqwY45.png",
    },
  ],
};

export default {
  name: "Home",
  components: {
    Stepper,
    FormStep1,
    FormStep2,
    FormStep3,
    CheckoutCart,
    Buttons,
  },
  data() {
    return {
      products: [],
      shippingFee: 0,
      step: 1,
    };
  },
  created() {
    this.fetchProducts();
  },
  methods: {
    fetchProducts() {
      this.products = DummyData.products;
    },
    handleShippingFee(shippingCost) {
      this.shippingFee = shippingCost;
    },
    buttonBackClicked(step) {
      this.step = step;
    },
    buttonNextClicked(step) {
      this.step = step;
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


