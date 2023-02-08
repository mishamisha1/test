<template>
  <div>
    <ProductCard v-for="product in products" :key="product.id" :product="product" />
  </div>
</template>

<script>
import ProductCard from '../src/components/ProductCard.vue';
import axios from 'axios';

export default {
  components: {
    ProductCard,
  },
  data() {
    return {
      products: [],
    };
  },
  mounted() {
    axios.get('https://fakestoreapi.com/products')
      .then(response => {
        this.products = response.data;
      });
  },
};
</script>