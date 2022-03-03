<template>



  <Login/>
  
  
</template>

<script>
import Login from '@/components/Login'

export default {
  name: 'Home',
  components: {Login}
}
</script>

<style>
.socials{
  padding: 5px;
  color: white;
}
#cardthing {
  background: rgba(0, 0, 0, 0.403);
}

.landing {
  top: 290px;
  left: 50px;
  position: relative;
  
}
.left-text{
  padding-left: 100px;
  text-align: left;
}

h1{
  color:#c36f09;
  font-weight:bold;
  text-shadow: 3px 3px 3px black;
}
h2{
  color:white;
  text-shadow: 3px 3px 3px black;
}
/* .row {
  width:45%;
  padding-top:20%;
  padding-left:15%;
} */

/* sign up form */

</style>