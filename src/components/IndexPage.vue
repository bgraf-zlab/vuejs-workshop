<template>
  <div>
    <product-list v-bind:products="products" v-on:addProduct="addProductToBasket" />
    <basket v-bind:products="productsInBasket" />
  </div>
</template>

<script>
import Basket from './Basket.vue';
import ProductList from './ProductList.vue';

export default {
  name: 'index-page',
  components: { Basket, ProductList },
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
    }
  }
}
</script>
