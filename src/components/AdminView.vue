<template>
  <div>
    <h2>Admin area: Add products</h2>
    <form>
      <input type="text" 
             placeholder="Enter product name" 
             v-model="name"
             class="form-control form-control-sm col-6 mb-2" />
      <input type="number" 
             placeholder="Price" 
             v-model="price"
             class="form-control form-control-sm col-3 mb-2" />
      <button class="btn btn-sm btn-primary" v-on:click.prevent="createProduct" :class="{ disabled: name === null }">
        Create product
      </button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'admin-view',
  data: function() {
		return {
      name: null,
      price: null,
    }
  },
  methods: {
    createProduct: function() {
      let product = {
        name: this.name,
        price: parseInt(this.price)
      }
      this.$emit('productCreated', product);
      this.name = null;
      this.price = null;
    }
  },
}
</script>

<style scoped>

</style>
