<template>
  <div id="app" class="container my-3 p-3">
    <h2>Products:</h2>
    <ul>
      <li v-for="product in products" class="m-2">
        <strong>
          {{ product.name }}: {{ product.price }}€
        </strong>
        <button class="btn btn-sm btn-primary"
                v-on:click="addProductToBasket(product)">
          Add to basket
        </button>
      </li>
    </ul>
    <basket v-bind:products="productsInBasket" />
  </div>
</template>

<script>
import Basket from './components/Basket.vue'

export default {
  name: 'app',
  components: { Basket },
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
