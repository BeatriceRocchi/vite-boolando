<script>
export default {};
</script>

<template>
  <header>
    <div class="container">
      <nav>
        <ul class="menu">
          <li><a href="#">Donna</a></li>
          <li><a href="#">Uomo</a></li>
          <li><a href="#">Bambini</a></li>
        </ul>
      </nav>
      <img src="../assets/img/boolean-logo.png" alt="Logo boolean" />
      <div>
        <i class="fa-regular fa-user"></i>
        <i class="fa-regular fa-heart"></i>
        <i class="fa-solid fa-bag-shopping"></i>
      </div>
    </div>
  </header>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables" as *;

header {
  background-color: $color-primary;
  color: $color-white;
  font-size: $font-m;
  height: 50px;
  // width: 100%;
  // position: fixed;
  // z-index: 100;
  box-shadow: 0 3px 5px rgba($color-black, 0.4);

  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 100%;

    .menu {
      display: flex;
      justify-content: space-between;

      li {
        padding-right: 10px;
      }
    }

    img {
      height: 25px;
    }

    i {
      padding-left: 10px;
    }
  }
}
</style>
