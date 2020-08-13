<template>
  <div id="app">
    <b-container class="col-md-3">
      <div>
        <ProductForm :storeProduct="storeProduct" :name="name" />
      </div>
      <div class="qtd-produtos-container">Quantidade de produtos: {{qtdProducts}}</div>
      <div class="product-list-container">
        <ProductsList :products="products" />
      </div>
    </b-container>
  </div>
</template>

<script>
import ProductForm from "./components/ProductForm";
import ProductsList from "./components/ProductsList";

export default {
  name: "App",
  components: {
    ProductForm,
    ProductsList,
  },
  data() {
    return {
      products: [],
      updated: false,
    };
  },
  computed: {
    qtdProducts() {
      return this.products.length;
    },
  },
  methods: {
    storeProduct(newProduct) {
      this.products.push(newProduct);
    },
  },
};
</script>

<style>
#app {
  margin-top: 40px;
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50; */
}
.qtd-produtos-container {
  margin-top: 20px;
}
.product-list-container {
  margin-top: 20px;
}
</style>
