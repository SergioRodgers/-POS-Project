<template>
  <Navbar/>


  <router-view></router-view>
  <Footer />
</template>
<script>
import Navbar from './components/Navbar.vue'
import Footer from './components/Footer.vue'
export default {
  components:{
    Navbar, Footer
  },
};
</script>
<style>
body{
  background-image: url(./assets/images/basketball.jpg);
  background-size:cover;
  
}
Footer{
  position: fixed;
  bottom:0;
  left: 0;
  width: 100%;

}


</style>
