<template>
  <HeaderArea/>
  <router-view/>
  <FooterArea/>
</template>
<script>
// import { defineComponent } from '@vue/composition-api'
import FooterArea from './layouts/FooterArea.vue';
import HeaderArea from './layouts/HeaderArea.vue';

export default {
  components:{
    HeaderArea,FooterArea
  },
  computed:{
    user(){
      return this.$store.state.user;
    }
  },
  setup() {
    
  },
}
</script>



<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
