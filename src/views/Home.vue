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
            <form class="card-body p-5 text-center">

              <div class="mb-md-5 mt-md-4 pb-5">

                <h1 class="fw-bold mb-2 text-uppercase">Login</h1>
                <p class="text-white-50 mb-5">Please enter your login and password!</p>

                <div class="form-outline form-white mb-4">
                  <input type="email" id="typeEmailX" class="form-control form-control-lg">
                  <label class="form-label" for="typeEmailX" style="margin-left: 0px;">Email</label>
                <div class="form-notch"><div class="form-notch-leading" style="width: 9px;"></div><div class="form-notch-middle" style="width: 40px;"></div><div class="form-notch-trailing"></div></div></div>

                <div class="form-outline form-white mb-4">
                  <div class="control">
                  <input type="password" id="typePasswordX" class="form-control form-control-lg">
                  </div>
                  
                  <label class="form-label" for="typePasswordX" style="margin-left: 0px;">Password</label>
                  <div class="form-notch"><div class="form-notch-leading" style="width: 9px;"></div><div class="form-notch-middle" style="width: 64.8px;"></div><div class="form-notch-trailing"></div></div>
                </div>
                

                <p class="small mb-5 pb-lg-2"><a class="text-white-50" href="#!">Forgot password?</a></p>

                <button class="btn btn-outline-light btn-lg px-5" type="submit" style="" onclick="">Login</button>

                <div class="d-flex justify-content-center text-center mt-4 pt-1">
                  <a href="#!" class="socials"><i class="fa fa-facebook-f"></i></a>
                  <a href="#!" class="socials"><i class="fa fa-twitter"></i></a>
                  <a href="#!" class="socials"><i class="fa fa-google"></i></a>
                </div>

              </div>

              <div>
                <p class="mb-0">Don't have an account? <a href="#!" class="text-white-50 fw-bold">Sign Up</a></p>
              </div>

            </form>
          </div>
        </div>
      </div>
  </div>
     
  </div>
  
</template>

<script>

</script>

<style>
.socials{
  padding: 5px;
  color: white;
}
#cardthing {
  background: rgba(0, 0, 0, 0.403);
}

body {
  overflow: hidden;
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