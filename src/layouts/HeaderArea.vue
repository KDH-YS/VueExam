<template>
  <div class="">
    <nav class="navbar navbar-expand-lg navbar-dark bg-dark">
      <div class="container-fluid">
        <a class="navbar-brand" href="#">Soldout</a>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
          <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav me-auto mb-2 mb-lg-0">
            <li class="nav-item">
              <router-link class="nav-link" to="/">홈</router-link>
            </li>
            <li class="nav-item">
              <rounter-link class="nav-link active" to="/">제품리스트</rounter-link>
            </li>
            <li class="nav-item">
              <router-link class="nav-link" to="/detail">제품상세페이지</router-link>
              </li>
            <li  class="nav-item">
              <!-- v-if="user.email!=undefined" -->
              <router-link class="nav-link" to="/sales">제품등록페이지</router-link>
            </li>
          <li v-if="this.$store.state.user === null" class="nav-item"><button class="btn btn-danger" type="button" @click="login">로그인</button></li>
          <li v-if="this.$store.state.user !== null" class="nav-item">
            <button class="btn btn-danger" type="button" @click="logout">로그아웃</button>
            <span style="color:white">{{this.$store.state.user.username}}</span>
          </li>          </ul>
          <form class="d-flex">
            <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search"> 
            <button class="btn btn-outline-success" type="submit">search</button>
          </form>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
  export default {
    name: 'HeaderArea',
    components: {

    },
    data() {
      return {

      };
    },
    setup() {

    },
    created() {

    },
    mounted() {

    },
    unmounted() {

    },
    methods: {
      login(){
        this.$router.push('/login');
      },
      logout(){
        this.$store.state.user = null;
      }

    }
  };
</script>

<style scoped>

</style>