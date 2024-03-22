<script>
import ProductCard from "./partials/ProductCard.vue";

export default {
  components: {
    ProductCard,
  },
};
</script>

<template>
  <main>
    <div class="container">
      <ProductCard />
      <ProductCard />
      <ProductCard />
      <ProductCard />
      <ProductCard />
      <ProductCard />
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
