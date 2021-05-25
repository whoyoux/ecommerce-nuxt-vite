<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">
        ecommerce
      </h1>
      <div v-for="product in products" :key="product.id">
        <h2>{{product.name}}</h2>
        <p>{{product.desc}}</p>
        <h3>{{parseFloat(product.price).toFixed(2)}}</h3>
        <img :src="product.photoUrl" :alt="product.name" width="125" height="125">
      </div>
    </div>
  </div>
</template>

<script>
import jsonProducts from "../store/store.json";
export default {
  data() {
    return {
      products: jsonProducts
    }
  },
  async created() {
    //console.log(jsonProducts); 
  }
}
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family:
    'Quicksand',
    'Source Sans Pro',
    -apple-system,
    BlinkMacSystemFont,
    'Segoe UI',
    Roboto,
    'Helvetica Neue',
    Arial,
    sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
