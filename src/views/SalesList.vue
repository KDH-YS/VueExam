<template>
<main class="mt-3">
  <div class="container">
    <div class="float-end mb-3">
      <button type="button" class="btn btn-dark" @click="addProduct">제품등록</button>
    </div>
    <table class="table table-bordered">
      <thead>
      <tr>
        <th>이미지</th>
        <th>제품번호</th>
        <th>제품명</th>
        <th>제품가격</th>
        <th>카테고리</th>
        <th></th>
      </tr>
      </thead>
      <tbody>
        <tr v-for="(product,idx) in ProductList" :key="idx">
          <td>
              <img :src="`/download/${product.path}`" alt="상품 이미지" style="height: 50px; width:auto;">
            </td>
            <td>{{ product.id }}</td>
            <td>{{ product.product_name}}</td>
            <td>{{ product.product_price.toLocaleString() }}원</td>
            <td>{{ product.category1 }}>{{ product.category2 }}>{{ product.category3 }}</td>
          <td>
            <button type="button" class="btn btn-info me-1">사진등록</button>
            <button type="button" class="btn btn-warning me-1">수정</button>
            <button type="button" class="btn btn-danger me-1"
            @click="deleteProduct(product.id)">삭제</button>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</main>
</template>

<script>
import {mapGetters, mapMutations} from 'vuex';
export default {
  name: 'SalesList',
  components: {
    
  },
  computed:{
    ...mapGetters({
      ProductList: 'ProductList',
    }),
    ProductList() {
      return this.$store.getters.ProductList('');
    },
  },
  methods: {
    ...mapMutations(['deleteProduct']),
    addProduct(){
      this.$router.push({path:'/create'})
    }
  }
};
</script>

<style scoped>

</style>