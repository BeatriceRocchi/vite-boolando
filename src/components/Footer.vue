<script>
export default {};
</script>

<template>
  <footer>
    <div class="container">
      <div>
        <h4>Boolando s.r.l</h4>
        <nav>
          <ul class="references">
            <li><a href="#">Informazioni legali</a></li>
            <li><a href="#">Informativa sulla privacy</a></li>
            <li><a href="#">DIritto di recesso</a></li>
          </ul>
        </nav>
      </div>
      <div>
        <h4>Trovaci anche su</h4>
        <div class="icons">
          <a href="#"><i class="fa-brands fa-square-twitter"></i></a>
          <a href="#"><i class="fa-brands fa-square-facebook"></i></a>
          <a href="#"><i class="fa-brands fa-square-instagram"></i></a>
          <a href="#"><i class="fa-brands fa-square-pinterest"></i></a>
          <a href="#"><i class="fa-brands fa-square-youtube"></i></a>
        </div>
      </div>
    </div>
  </footer>
</template>

<style lang="scss" scoped>
@use "../assets/scss/partials/variables" as *;

footer {
  background-color: $color-secondary;
  font-size: $font-m;
  color: $color-white;
  padding: 20px 0;

  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;

    .references {
      display: flex;
      justify-content: space-between;
      padding-top: 8px;

      li {
        margin-right: 10px;
        font-size: $font-xs;
        &:hover {
          text-decoration: underline;
        }
      }
    }

    .icons i {
      margin-right: 6px;
      font-size: $font-l;
      padding-top: 8px;
    }
  }
}
</style>
