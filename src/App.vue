<template>
  <div id="app" class="container my-4 p-4">
    <img src="./assets/logo.png" class="float-right">
    <product-list v-on:addProduct="addProductToBasket" />
    <basket v-bind:products="productsInBasket" />
  </div>
</template>

<script>
import Basket from './components/Basket.vue';
import ProductList from './components/ProductList.vue';

export default {
  name: 'app',
  components: { Basket, ProductList },
  data: function() {
    return {
      productsInBasket: []
    }
  },
  methods: {
  	addProductToBasket: function(product) {
    	this.productsInBasket.push(product);
    },
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
