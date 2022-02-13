<template>
  <footer>
    <section class="footer-container d-flex justify-content-around">
      <div>
        <img class="footer-logo" src="https://i.imgur.com/czHV17Z.png" alt="" />
      </div>
      <div class="footer-service d-flex flex-column">
        <span class="service-title">客戶服務</span>
        <span class="service-link">運送說明</span>
        <span class="service-link">退換貨相關</span>
        <span class="service-link">付款資訊</span>
        <span class="service-link">FAQ</span>
      </div>
      <div class="footer-about d-flex flex-column">
        <span class="about-title">關於我們</span>
        <span class="about-link">品牌故事</span>
        <span class="about-link">媒體聯繫</span>
        <span class="about-link">Press kit</span>
      </div>
      <div class="footer-info d-flex flex-column">
        <span class="info-title">資訊</span>
        <span class="info-link">隱私權政策</span>
        <span class="info-link">Cookie</span>
        <span class="info-link">GDPR</span>
      </div>
      <div class="footer-social d-flex flex-column">
        <span class="social-title">追蹤 Alpha Shop</span>
        <span class="social-phone">+886 02123 45678</span>
        <ul class="social-links d-flex align-items-center">
          <li class="social-link">
            <a href=""><img src="https://i.imgur.com/EszXNpc.png" alt="" /></a>
          </li>
          <li class="social-link">
            <a href=""><img src="https://i.imgur.com/pDe5FmA.png" alt="" /></a>
          </li>
          <li class="social-link">
            <a href=""><img src="https://i.imgur.com/srh83te.png" alt="" /></a>
          </li>
        </ul>
      </div>
    </section>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style lang="scss" scoped>
@import "../style/reset.scss";
/* Footer Section */

.footer-container {
  padding: 2rem;
  background-color: $footer-gray;
}

.footer-logo {
  width: 230px;
  height: auto;
}

.service-title,
.about-title,
.info-title,
.social-title {
  font-size: 1.5rem;
  font-weight: 700;
  margin: 1rem 0;
}

.service-link,
.about-link,
.info-link,
.social-phone {
  color: $dark-gray;
}

.social-link {
  width: 32px;
  height: 28px;
  margin-top: 3px;
  margin-right: 3px;
}
</style>
