<template>
  <div id="app" class="container my-4 p-4">
    <img src="./assets/logo.png" class="float-right">
    <product-list v-bind:products="products" v-on:addProduct="addProductToBasket" />
    <basket v-bind:products="productsInBasket" />
    <admin-view v-on:productCreated="handleProductCreation" />
  </div>
</template>

<script>
import Basket from './components/Basket.vue';
import ProductList from './components/ProductList.vue';
import AdminView from './components/AdminView.vue';

export default {
  name: 'app',
  components: { Basket, ProductList, AdminView },
  data: function() {
    return {
      products: [
        { name: 'Schaufel', price: 50 },
        { name: 'Fork', price: 70 }
      ],
      productsInBasket: []
    }
  },
  methods: {
  	addProductToBasket: function(product) {
    	this.productsInBasket.push(product);
    },
    handleProductCreation: function(product) {
      this.products.push(product);
    }
  }
}
</script>

<style>
body {
  background-color: #333;
}

#app {
  background-color: #fff;
  border-radius: 8px;
}
</style>
