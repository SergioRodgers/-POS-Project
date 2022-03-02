<template>
  <div class="column">
  <div class="row">
    <div class="col-5 landing">
      <div class="left-text">
          <h1>BallersUnited</h1>
    <h2>Join our community of Ballers and get 20% off your first purchase!!</h2> 
      </div>    
    </div>
  </div>
</div>
  
      <!-- Sign Up -->

<div class="column">
  <div class="row">
    <div class="row d-flex justify-content-center">
         <div class="col-6"></div>
    <div class="col-6 col-md-3 col-lg-6 col-xl-4">
          <div class="card text-white" id="cardthing" style="border-radius: 1rem; heigt:30%;">
            <form class="card-body p-5 text-center" @submit.prevent="login">

              <div class="mb-md-5 mt-md-4 pb-5">

                <h1 class="fw-bold mb-2 text-uppercase">Login</h1>
                <p class="text-white-50 mb-5">Please enter your login and password!</p>

                <div class="form-outline form-white mb-4">
                  <input type="email" id="typeEmailX" v-model="email" class="form-control form-control-lg">
                  <label class="form-label text-dark" for="typeEmailX" style="margin-left: 0px;">Email</label>
                <div class="form-notch"><div class="form-notch-leading" style="width: 9px;"></div><div class="form-notch-middle" style="width: 40px;"></div><div class="form-notch-trailing"></div></div></div>

                <div class="form-outline form-white mb-4">
                  <input type="password" id="typePasswordX" v-model="password"  class="form-control form-control-lg">
                  <label class="form-label text-dark" for="typePasswordX" style="margin-left: 0px;">Password</label>
                <div class="form-notch"><div class="form-notch-leading" style="width: 9px;"></div><div class="form-notch-middle" style="width: 64.8px;"></div><div class="form-notch-trailing"></div></div></div>

                <p class="small mb-5 pb-lg-2"><a class="text-white-50" href="#!">Forgot password?</a></p>

                <button class="btn btn-outline-light btn-lg px-5" type="submit">Login</button>

                <div class="d-flex justify-content-center text-center mt-4 pt-1">
                  <a href="#!" class="text-white"><i class="fab fa-facebook-f fa-lg"></i></a>
                  <a href="#!" class="text-white"><i class="fab fa-twitter fa-lg mx-4 px-2"></i></a>
                  <a href="#!" class="text-white"><i class="fab fa-google fa-lg"></i></a>
                </div>

              </div>

              <div>
                <p class="mb-0">Don't have an account? <span type="button" class="btn " data-bs-toggle="modal" data-bs-target="#exampleModal">Sign Up</span></p>
              </div>

              <Modal/>
              <!-- END -->
            </form>
          </div>
        </div>
      </div>
  </div>
     
  </div>
</template>

<script>
import Modal from './Modal.register.vue'
export default {
    data() {
        return {
            email: "",
            password: ""
        }
    },
    components:{Modal},
    methods: {
    login() {
      fetch("https://balls-united.herokuapp.com/users", {
        method: "PATCH",
        body: JSON.stringify({
          email: this.email,
          password: this.password,
        }),
        headers: {
          "Content-type": "application/json; charset=UTF-8",
        },
      })
        .then((response) => response.json())
        .then((json) => {
          localStorage.setItem("jwt", json.jwt);
          alert("User logged in");
          this.$router.push({ name: "Dashboard" });
        })
        .catch((err) => {
          alert(err);
        });
    },
  },

}
</script>

<style>

</style>