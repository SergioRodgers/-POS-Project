<template>
  <h1>This is Signup Page</h1>

    <div class="row">
    <div class="row d-flex justify-content-center">
         
    <div class="col-8">
          <div class="card text-white" id="cardthing" style="border-radius: 1rem; heigt:30%;">
            <form class="card-body p-5 text-center" @submit.prevent="login">

              <div class="mb-md-5 mt-md-4 pb-5">

                <h1 class="fw-bold mb-2 text-uppercase">Signup</h1>
                <p class="text-white-50 mb-5">Welcome!</p>

                <div class="names row">
                  <div class="form-outline form-white mb-4 col-xs-12 col-md-6">
                  <input type="name" id="typeName" v-model="password"  class="form-control form-control-lg">
                  <label class="form-label" for="typeName" style="margin-left: 0px;">Name</label>
                <div class="form-notch"><div class="form-notch-leading" style="width: 9px;"></div><div class="form-notch-middle" style="width: 64.8px;"></div><div class="form-notch-trailing"></div></div></div>

                   <div class="form-outline form-white mb-4 col-xs-12 col-md-6">
                  <input type="name" id="typeName" v-model="password"  class="form-control form-control-lg">
                  <label class="form-label" for="typeName" style="margin-left: 0px;">Lastname</label>
                <div class="form-notch"><div class="form-notch-leading" style="width: 9px;"></div><div class="form-notch-middle" style="width: 64.8px;"></div><div class="form-notch-trailing"></div></div></div>

                </div>
                
                <div class="logins row">
                   <div class="form-outline form-white mb-4 col-xs-12 col-md-6">
                  <input type="email" id="typeEmail" v-model="password"  class="form-control form-control-lg">
                  <label class="form-label" for="typeEmail" style="margin-left: 0px;">Email</label>
                <div class="form-notch"><div class="form-notch-leading" style="width: 9px;"></div><div class="form-notch-middle" style="width: 64.8px;"></div><div class="form-notch-trailing"></div></div></div>

                <div class="form-outline form-white mb-4 col-xs-12 col-md-6">
                  <input type="password" id="typePasswordX" v-model="password"  class="form-control form-control-lg">
                  <label class="form-label" for="typePasswordX" style="margin-left: 0px;">Password</label>
                <div class="form-notch"><div class="form-notch-leading" style="width: 9px;"></div><div class="form-notch-middle" style="width: 64.8px;"></div><div class="form-notch-trailing"></div></div></div>


                </div>

                <button class="btn btn-outline-light btn-lg px-5" type="submit">Sign up</button>

              </div>

              <div>
                <p class="mb-0">Already a member? <router-link :to="{name: 'Home'}" class="text-white-50 fw-bold">Sign in</router-link></p>
              </div>

            </form>
          </div>
        </div>
      </div>
  </div>

 <!-- Button trigger modal -->

</template>

<script>
export default {

}
</script>

<style>

</style>