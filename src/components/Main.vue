<script>
import ProductCard from "./partials/ProductCard.vue";
import products from "../assets/data/db.js";

// COSA CAMBIA USANDO DB in JSON:
//Partendo da db2 in json, istruzione di import diventa:
// import products from "../assets/data/db2.json";
//E in v-for il ciclo è in products.products
//Il resto funziona uguale

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
        v-for="(product, index) in products"
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
