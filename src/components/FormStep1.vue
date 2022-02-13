<template>
  <div class="form-part">
    <h1 class="form-part-title">寄送地址</h1>
    <div class="form-group">
      <div class="form-row prefix">
        <label for="">稱謂</label>
        <div>
          <select name="prefix" id="prefix">
            <option value="ms" selected>小姐</option>
            <option value="mr">先生</option>
          </select>
        </div>
      </div>
      <div class="form-row name">
        <label for="">姓名</label>
        <input id="name" type="text" placeholder="請輸入姓名" />
      </div>
    </div>
    <div class="form-group">
      <div class="form-row phone">
        <label for="">電話</label>
        <div>
          <input id="phone" type="number" placeholder="請輸入行動電話" />
        </div>
      </div>
      <div class="form-row email">
        <label for="">Email</label>
        <div><input id="email" type="text" placeholder="請輸入電子郵件" /></div>
      </div>
    </div>
    <div class="form-group">
      <div class="form-row city">
        <label for="">縣市</label>
        <div class="select-wrapper">
          <select name="a-location" id="a-location" required>
            <option value="" disabled selected>請選擇縣市</option>
            <option value="">臺北市</option>
            <option value="">新北市</option>
            <option value="">基隆市</option>
            <option value="">桃園市</option>
            <option value="">苗栗縣</option>
            <option value="">臺中市</option>
            <option value="">臺南市</option>
            <option value="">高雄市</option>
            <option value="">基隆市</option>
            <option value="">新竹市</option>
            <option value="">嘉義市</option>
            <option value="">新竹縣</option>
            <option value="">彰化縣</option>
            <option value="">南投縣</option>
            <option value="">雲林縣</option>
            <option value="">嘉義縣</option>
            <option value="">屏東縣</option>
            <option value="">宜蘭縣</option>
            <option value="">台東縣</option>
            <option value="">澎湖縣</option>
          </select>
        </div>
      </div>
      <div class="form-row address">
        <label for="">地址</label>
        <div><input id="address" type="text" placeholder="請輸入地址" /></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "FormStep1",
};
</script>

<style lang="scss" scoped>
@import "../style/reset.scss";
@import "../style/mixin.scss";
@import "../style/each.scss";
@import "../style/panel.scss";
</style>
