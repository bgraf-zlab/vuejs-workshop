<template>
  <strong>
    {{ name }}: {{ price }}€ 💵
  </strong>
</template>

<script>
export default {
  name: 'product',
  props: [
    'name',
    'price'
  ]
}
</script>

<style scoped>

</style>
