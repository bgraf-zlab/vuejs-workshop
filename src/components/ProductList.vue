<template>
  <div>
    <h2>Products:</h2>
    <ul>
      <li v-for="product in products" class="m-2">
        <product v-bind:name="product.name" v-bind:price="product.price"></product>
        <button class="btn btn-sm btn-primary"
                v-on:click="addProductToBasket(product)">
          Add to basket
        </button>
      </li>
    </ul>
  </div>
</template>

<script>
import Product from './Product.vue'

export default {
  name: 'product-list',
  components: { Product },
  data: function() {
		return {
    }
  },
  props: [
    'products'
  ],
  methods: {
  	addProductToBasket: function(product) {
      this.$emit('addProduct', product)
    }
  },
}
</script>

<style scoped>

</style>
