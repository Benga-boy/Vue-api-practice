<template>
  <div class="container" v-if="product">
    <ProductCard :title="product.title" :image="product.image" :description="product.description" :id="product.id" :price="product.price" />
  </div>
</template>

<script>
import ProductCard from '../components/Product'
import axios from 'axios'

export default {
  name: 'ProductItem',
  components: {ProductCard},
  data() {
    return {
      product: {}
    }
  },
  async created() {
    try {
      const res = await axios.get(`https://fakestoreapi.com/products/${this.$route.params.id}`)
      this.product = res.data
    } catch (err) {
      console.log(err)
    }
  }
}
</script>

<style>

</style>