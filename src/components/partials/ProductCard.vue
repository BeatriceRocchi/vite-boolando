<script>
export default {
  props: {
    productObject: Object,
  },
  methods: {
    calcSalesPrice() {
      let salesPrice;
      this.productObject.badges.forEach((badge) => {
        if (badge.type === "discount") {
          salesPrice =
            this.productObject.price -
            this.productObject.price * Math.abs(parseFloat(badge.value) / 100);
        }
      });
      return salesPrice ? salesPrice.toFixed(2) : null;
    },
  },
};
</script>

<template>
  <div class="card">
    <div class="top-card">
      <img
        class="default-img"
        :src="`/src/assets/img/${productObject.frontImage}`"
        :alt="productObject.brand"
      />
      <img
        class="hover-img"
        :src="`/src/assets/img/${productObject.backImage}`"
        :alt="productObject.brand"
      />
      <div class="wish">&hearts;</div>
      <div class="badges-box">
        <span
          v-for="(badge, index) in productObject.badges"
          :key="index"
          :class="badge.type"
        >
          {{ badge.value }}</span
        >
      </div>
    </div>
    <div class="bottom-card">
      <div class="brand">{{ productObject.brand }}</div>
      <div class="product">{{ productObject.name }}</div>
      <div>
        <span v-if="calcSalesPrice()" class="discounted-price"
          >{{ calcSalesPrice() }} &euro;
        </span>
        <span class="full-price" :class="{ strike: calcSalesPrice() }">
          {{ productObject.price }} &euro;</span
        >
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

    .badges-box {
      position: absolute;
      bottom: 8%;
      font-size: $font-s;
      font-weight: bold;
      color: $color-white;

      .discount,
      .tag {
        padding: 5px 12px;
      }

      .discount {
        background-color: $color-discount;
      }

      .tag {
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

    .strike {
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
