<template>
  <div class="form-part" @change="shippingCostSelected">
    <h1 class="form-part-title">運送方式</h1>
    <div class="shippings-wrapper">
      <div class="shippings" v-for="shipping in shippings" :key="shipping.id">
        <div class="shipping-radio">
          <input
            name="shipping"
            type="radio"
            :value="shipping.cost"
            v-model="cost"
          />
        </div>
        <label for="" class="shipping">{{ shipping.name }}</label>
        <h4 class="shipping-details">{{ shipping.details }}</h4>
        <h4 class="shipping-cost">{{ shipping.cost | ifFree }}</h4>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FormStep2",
  data() {
    return {
      shippings: [
        {
          id: 1,
          name: "標準配送",
          details: "約3 ~ 7個工作天",
          cost: 0,
          value: "standard-shipping",
        },
        {
          id: 2,
          name: "DHL 貨運",
          details: "48小時內送達",
          cost: 500,
          value: "DHL-shipping",
        },
      ],
    };
  },
  methods: {
    shippingCostSelected() {
      this.$emit("shippingCostSelected", this.cost);
    },
  },
  filters: {
    ifFree(n) {
      return n === 0 ? "免費" : "$" + n;
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
