<template>
  <div>
    <h2>Basket:</h2>
    <ul v-if="products.length !== 0">
      <li v-for="product in products" class="m-2">
        <product v-bind:name="product.name" v-bind:price="product.price"></product>
        <button class="btn btn-sm btn-danger"
                v-on:click="removeProduct(product)">
          Remove
        </button>
      </li>
      <li>
        <strong>Sum: {{ basketSum }}€</strong>
      </li>
    </ul>
    <p v-else>
      Your basket is still empty. Why don't you add something?
    </p>
  </div>
</template>

<script>
import Product from './Product.vue'

export default {
  name: 'basket',
  components: { Product },
  props: [
    'products'
  ],
  data: function() {
		return { }
  },
  computed: {
    basketSum: function() {
      return this.products.reduce((sum, product) => sum + product.price, 0);
    }
  },
  methods: {
    removeProduct: function (product) {
      this.products.splice(this.products.indexOf(product), 1);
    }
  },
}
</script>

<style scoped>

</style>
