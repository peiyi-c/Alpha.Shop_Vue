<template>
  <header>
    <div class="nav-menu">
      <ul class="nav-items d-flex" id="nav-items">
        <li class="nav-item">
          <a href="" class="nav-item-link">男款</a>
        </li>
        <li class="nav-item">
          <a href="" class="nav-item-link">女款</a>
        </li>
        <li class="nav-item">
          <a href="" class="nav-item-link">最新消息</a>
        </li>
        <li class="nav-item">
          <a href="" class="nav-item-link">客製商品</a>
        </li>
        <li class="nav-item">
          <a href="" class="nav-item-link">聯絡我們</a>
        </li>
      </ul>
      <ul class="nav-menu-logo">
        <a href="" class="nav-menu-link"
          ><img src="https://i.imgur.com/gvRKoTR.png" alt=""
        /></a>
      </ul>
      <ul class="nav-icons" id="nav-icons">
        <li class="nav-icon">
          <a href="#" class="nav-icon-link"
            ><img src="https://i.imgur.com/hMJxRNK.png" alt=""
          /></a>
        </li>
        <li class="nav-icon">
          <a href="#" class="nav-icon-link"
            ><img src="https://i.imgur.com/hQ161De.png" alt=""
          /></a>
        </li>
        <li class="nav-icon">
          <a href="#" class="nav-icon-link"
            ><img src="https://i.imgur.com/jGuYxG9.png" alt=""
          /></a>
        </li>
      </ul>
    </div>
  </header>
</template>

<script>
export default {
  name: "Navigation",
};
</script>

<style lang="scss" scoped>
@import "../style/reset.scss";

header {
  z-index: 200;
}

.nav-toggle {
  visibility: hidden;
}

.nav-toggle:checked ~ .nav-menu {
  display: block;
  transform: scale(1, 1);
}

.nav-toggle-label {
  margin-left: $spacer;
  display: flex;
  align-items: center;
  .nav-vector {
    position: absolute;
    width: 15px;
    height: 3px;
    background: $almost-black;
  }
  .nav-vector::before {
    width: 10px;
    height: 3px;
    background: $almost-black;
  }
  .nav-vector::after {
    width: 20px;
    height: 3px;
    background: $almost-black;
  }
  .nav-vector::before,
  .nav-vector::after {
    position: absolute;
    content: "";
  }
  .nav-vector::before {
    top: 0.5rem;
  }
  .nav-vector::after {
    bottom: 0.5rem;
  }
}

.nav-logo {
  display: flex;
  justify-content: center;
  height: 3rem;
  min-width: 17rem;
}

.nav-menu {
  position: absolute;
  width: 100%;
  transition: transform 0.7s ease-out;
  transform-origin: top;
  transform: scale(1, 0);
  background-color: $white;
}

.nav-items {
  flex-direction: column;
  align-items: center;

  .nav-item {
    border-bottom: 2px solid $sky-gray;
    width: 100%;
    text-align: center;
    padding: 1rem;
  }
}

.nav-menu-logo {
  display: none;
}

.nav-icons {
  display: flex;
  justify-content: center;

  .nav-icon {
    margin: 1.5rem;
    height: 1.5rem;
    width: 1.5rem;
  }
}

////////////******電腦版******////////////

.nav-toggle,
.nav-toggle-label,
.nav-logo {
  display: none;
}
.nav-menu {
  all: unset;
  display: grid;
  grid-template-columns: 4.5fr 5.5fr;
  position: relative;
}
.nav-menu-logo {
  display: block;
  position: absolute;
  top: 5px;
  left: 45%;
  height: 2rem;
  width: 12rem;
  margin: 1rem;
}
.nav-items {
  flex-direction: row;
  margin-left: 30px;
  .nav-item {
    border-bottom: none;
  }
}
.nav-icons {
  display: flex;
  justify-content: flex-end;
  margin-right: 1.6rem;
  align-items: center;
}
</style>
