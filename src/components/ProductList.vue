<template>
    <ul class="catalog__list">
      <ProductItem v-for="product in products" :key="product.id" :product="product" ></ProductItem>
    </ul>
</template>

<script>
import ProductItem from '@/components/ProductItem.vue';

export default {
  name: 'ProductList',
  components: { ProductItem },
  props: ['products'],
};
</script>
