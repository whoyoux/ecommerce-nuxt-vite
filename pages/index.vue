<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">ecommerce</h1>
      <div class="centerWrapper">
        <div class="products">
          <div v-for="product in products" :key="product.id" class="product">
            <img
              :src="product.photoUrl"
              :alt="product.name"
              width="125"
              height="125"
            />
            <h2>{{ product.name }}</h2>
            <p>{{ product.desc }}</p>
            <h3>$ {{ parseFloat(product.price).toFixed(2) }}</h3>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import jsonProducts from "../store/store.json";
export default {
  data() {
    return {
      products: jsonProducts,
    };
  },
  async created() {
    //console.log(jsonProducts);
  },
};
</script>

<style>
.centerWrapper {
  display: grid;
  justify-content: center;
}
</style>
