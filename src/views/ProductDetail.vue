<template>
  <div class="">
      <h1>상품 상세페이지</h1>
      <div v-if="product">
        <img :src="`/download/${product.path}`" alt="상품이미지">
        <h2>{{product.product_name}}</h2>
        <p>{{product.product_price.toLocaleString()}}원</p>
      </div>
      <div v-else>
        <p>상품을 찾을 수 없습니다</p>
      </div>
  </div>
  <div> 
    <router-link to="/">돌아가기</router-link>
  </div>
</template>

<script>
import {mapGetters} from 'vuex';
export default {
  name: 'ProductDetail',
  computed:{
    ...mapGetters(['ProductList']),
    product(){
      const product_id = Number(this.$route.query.id);
      const products = this.ProductList();
      return products.find(p=> p.id=== product_id) || null;
    }
  },
  components: {
    
  },
};
</script>

<style scoped>

</style>