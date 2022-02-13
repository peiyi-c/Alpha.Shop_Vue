<template>
  <div>
    <h1 class="panel-title">結帳</h1>
    <div class="panel-stepper">
      <div id="step-control" class="steps-container d-flex">
        <div class="step" :class="{ active: step === 1 }">
          <div class="circle-container"></div>
          <div class="label-container">寄送地址</div>
        </div>
        <div class="step" :class="{ active: step === 2 }">
          <div class="circle-container"></div>
          <span class="connect-line"></span>
          <div class="label-container">運送方式</div>
        </div>
        <div class="step" :class="{ active: step === 3 }">
          <div class="circle-container"></div>
          <span class="connect-line"></span>
          <div class="label-container">付款資訊</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Stepper",
  props: {
    step: {
      type: Number,
      require: true,
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