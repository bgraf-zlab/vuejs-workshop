<template>
  <div>
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
  </div>
</template>

<script>
export default {
  name: 'product-list',
  data: function() {
		return {
      products: [
        { name: 'Schaufel', price: 50 },
        { name: 'Fork', price: 70 }
      ]
    }
  },
  methods: {
  	addProductToBasket: function(product) {
      this.$emit('addProduct', product)
    }
  },
}
</script>

<style scoped>

</style>
