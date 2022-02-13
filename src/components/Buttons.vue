<template>
  <div id="btn-control" class="panel-buttons d-flex justify-conotent-end">
    <button
      class="panel-button button-back"
      v-if="step !== 1"
      @click.stop.prevent="buttonBackClicked"
    >
      上一步
    </button>
    <button
      class="panel-button button-next"
      @click.stop.prevent="buttonNextClicked"
      v-if="step !== 3"
    >
      下一步
    </button>
    <button class="panel-button button-next" v-if="step === 3">送出訂單</button>
  </div>
</template>

<script>
export default {
  name: "Buttons",
  props: {
    InitialStep: {
      type: Number,
      require: true,
    },
  },
  data() {
    return {
      step: this.InitialStep,
    };
  },
  methods: {
    buttonBackClicked() {
      this.step--;
      this.$emit("button-back-clicked", this.step);
    },
    buttonNextClicked() {
      if (this.step <= 2) {
        this.step++;
        this.$emit("button-next-clicked", this.step);
      } else {
        return this.step;
      }
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