<script>
export default {};
</script>

<template>
  <div class="card">
    <div class="top-card">
      <img class="default-img" src="../../assets/img/1.webp" alt="Levi's" />
      <img
        class="hover-img"
        src="../../assets/img/1b.webp"
        alt="T-shirt Levi's"
      />
      <div class="wish">&hearts;</div>
      <div class="tag">
        <span class="discount">-50%</span>
        <span class="sustainability">Sostenibilità</span>
      </div>
    </div>
    <div class="bottom-card">
      <div class="brand">Levi's</div>
      <div class="product">relaxed fit tee unisex</div>
      <div>
        <span class="discounted-price">14,99 &euro;</span
        ><span class="full-price"> 29,99 &euro;</span>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@use "../../assets/scss/partials/variables" as *;

.card {
  width: 32%;
  margin: 20px 0;

  .top-card {
    position: relative;
    height: 500px;

    img {
      object-fit: cover;
      object-position: center;
      width: 100%;
      height: 100%;
    }

    .hover-img {
      display: none;
    }

    .wish {
      background-color: $color-white;
      font-size: $font-xl;
      padding: 5px 12px;
      position: absolute;
      right: 0;
      top: 2%;

      &:hover {
        color: $color-discount;
      }
    }

    .tag {
      position: absolute;
      bottom: 8%;
      font-size: $font-s;
      font-weight: bold;
      color: $color-white;

      .discount,
      .sustainability {
        padding: 5px 12px;
      }

      .discount {
        background-color: $color-discount;
      }

      .sustainability {
        background-color: $color-value;
      }
    }
  }
  .bottom-card {
    font-size: $font-s;

    .product {
      font-weight: bold;
      text-transform: uppercase;
      font-size: $font-m;
    }

    .discounted-price {
      font-weight: bold;
      color: $color-discount;
    }

    .full-price {
      text-decoration: line-through;
    }
  }

  &:hover {
    .hover-img {
      display: block;
    }

    .default-img {
      display: none;
    }
  }
}
</style>
