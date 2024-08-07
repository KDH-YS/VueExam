<template>
  <div class="container mt-4">
    <h1 class="mb-4">상품등록</h1>
    <form>
      <div class="mb-3">
        <label for="name" class="form-label">상품명</label>
        <input type="text" v-model="newProduct.product_name" class="form-control" id="name" placeholder="상품명을 입력하세요">
      </div>
      <div class="mb-3">
        <label for="price" class="form-label">가격</label>
        <input type="text" v-model="newProduct.product_price" class="form-control" id="price" placeholder="가격을 입력하세요">
      </div>
      <div class="mb-3">
        <label for="path" class="form-label">이미지</label>
        <input type="text" v-model="newProduct.path" class="form-control" id="path"  placeholder="이미지 경로를 입력하세요">
      </div>
      <div class="mb-3">
        <label for="category1" class="form-label">카테고리1</label>
        <select v-model="newProduct.category1" class="form-select" id="category1">
          <option value="">선택하세요</option>
          <option value="전자기기">전자기기</option>
          <option value="악세서리">악세서리</option>
        </select>
      </div>
      <div class="mb-3">
        <label for="category2" class="form-label">카테고리2</label>
        <select v-model="newProduct.category2" class="form-select" id="category2">
          <option value="">선택하세요</option>
          <option value="노트북">노트북</option>
          <option value="PC용품">PC용품</option>
        </select>
      </div>
      <div class="mb-3">
        <label for="category3" class="form-label">카테고리3</label>
        <select v-model="newProduct.category3" class="form-select" id="category3">
          <option value="">선택하세요</option>
          <option value="게이밍">게이밍</option>
          <option value="무선">무선</option>
        </select>
      </div>
      <button type="submit" class="btn btn-primary" @click="addGood">등록</button>
    </form>
  </div>
</template>

<script>
export default {
  name: 'ProductCreate',
  data() {
    return {
      newProduct: {
        product_name: '',
        product_price: '',
        path: '',
        category1: '',
        category2: '',
        category3: '',
      },
    };
  },
  methods:{
    addGood(){
      this.$store.commit('addProduct', this.newProduct);
      this.$router.push('/sales');
      
    }  }
};
</script>

<style scoped>
</style>
