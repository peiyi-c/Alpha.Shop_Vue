<template>
  <div class="form-part">
    <h1 class="form-part-title">付款資訊</h1>
    <div class="form-group">
      <div class="form-row card-holder">
        <label for="">持卡人姓名</label>
        <input id="card-holder" type="text" placeholder="John Doe" />
      </div>
    </div>
    <div class="form-group">
      <div class="form-row card-number">
        <label for="">卡號</label>
        <input
          id="card-number"
          type="number"
          placeholder="1111 2222 3333 4444"
        />
      </div>
    </div>
    <div class="form-group">
      <div class="form-row valid">
        <label for="">有效期限</label>
        <input id="valid" type="number" placeholder="MM/YY" />
      </div>
      <div class="form-row cvc-ccv">
        <label for="">CVC/CCV</label>
        <input id="cvc-ccv" type="number" placeholder="123" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FormStep3",
};
</script>

<style lang="scss" scoped>
@import "../style/reset.scss";
@import "../style/mixin.scss";
@import "../style/each.scss";
@import "../style/panel.scss";
</style>
