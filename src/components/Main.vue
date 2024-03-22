<script>
import ProductCard from "./partials/ProductCard.vue";
import products from "../assets/data/db.json";

export default {
  components: {
    ProductCard,
  },

  data() {
    return {
      products,
    };
  },
};
</script>

<template>
  <main>
    <div class="container">
      <ProductCard
        v-for="(product, index) in products.products"
        :key="`product-${index}`"
        :productObject="product"
      />
    </div>
  </main>
</template>

<style lang="scss" scoped>
main {
  padding-top: 80px;

  .container {
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
  }
}
</style>
