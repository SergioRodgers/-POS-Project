<template>
  <Navbar/>
  <router-view></router-view>
</template>
<script>
import Navbar from './components/Navbar.vue'
export default {
  components:{
    Navbar
  }
}
</script>
<style>
body{
  background-image: url(./assets/images/basketball.jpg);
  background-size:cover;
   overflow:none !important;
}


</style>
