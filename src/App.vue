<script>
import ProductList from './components/ProductList.vue'
import axios from './api/api'

export default {
  data() {
    return {
      products: []
    }
  },

  mounted() {
    axios.get(`products`).then((res) => (this.products = res.data))
  }
}
</script>

<script setup>
import MyHeader from './components/MyHeader.vue'
</script>

<template>
  <my-header></my-header>
  <product-list :products="products"></product-list>
</template>

<style scoped lang="scss"></style>
