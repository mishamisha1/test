<template>
  <div
    class="product-card"
    :style="{ transform: expanded ? 'scale(0.5)' : 'scale(1)' }"
    @mouseenter="expanded = true"
    @mouseleave="expanded = false"
  >
    <img :src="product.image" alt="product image" />
    <h3>{{ product.title }}</h3>
    <p>{{ product.price }}</p>
    <template v-if="expanded">
      <p>{{ product.description }}</p>
      <p>SKU: {{ product.sku }}</p>
    </template>
  </div>
</template>

<script>
export default {
  props: {
    product: Object,
  },
  data() {
    return {
      expanded: false,
    };
  },
};
</script>

<style>
.product-card {
  width: 1300px;
  height: 1500px;
  margin: 16px;
  overflow: hidden;
  transition: transform 0.5s ease;
}
</style>