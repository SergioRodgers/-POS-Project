<template>
  <!-- START -->
                <!-- Modal -->
                <div class="modal fade" id="exampleModal" tabindex="-1" aria-labelledby="exampleModalLabel" aria-hidden="true">
                  <div class="modal-dialog">
                    <div class="modal-content">
                      <div class="modal-header">
                        <h5 class="modal-title text-dark" id="exampleModalLabel">Create an account</h5>
                        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                      </div>
                      <form @submit.prevent="signup">
                      <div class="modal-body">
                        <!-- BODY START -->
                          
                       
                         

                        <div class="form-outline mb-4">
                        <input type="text" id="form3Example1cg" v-model="fullname" class="form-control form-control-lg" placeholder="name surname"/>
                      </div>

                <div class="form-outline mb-4">
                  <input type="email" id="form3Example3cg" v-model="email" class="form-control form-control-lg" placeholder="username@example.com"/>
                </div>

                <div class="form-outline mb-4">
                  <input type="password" id="form3Example4cg" v-model="password" class="form-control form-control-lg" placeholder="password"/>
                  
                </div>

                <div class="form-outline mb-4">
                  <input type="text" id="form3Example4cdg" v-model="contact" class="form-control form-control-lg" placeholder="081456987" />
                
                </div>

                

                <!-- <div class="d-flex justify-content-center">
                  <button type="button" class="btn btn-outline-warning btn-block btn-lg text-body">Register</button>
                </div> -->

           
              

          

                        <!-- BODY END -->
                      </div>
                      <div class="modal-footer">
                        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                        <button type="submit" class="btn btn-primary" data-bs-dismiss="modal">Register</button>
                      </div>
                      </form>
                    </div>
                  </div>
                </div>

</template>

<script>
export default {
    data(){
        return {
            fullname: "",
            email: "",
            password: "",
            contact: ""
        }
    },
    methods: {
    signup() {
      fetch("https://balls-united.herokuapp.com/users", {
        method: "POST",
        body: JSON.stringify({
          fullname: this.fullname,
          email: this.email,
          contact: this.contact,
          password: this.password,
        }),
        headers: {
          "Content-type": "application/json; charset=UTF-8",
        },
      })
        .then((response) => response.json())
        .then((json) => {
          alert("User registered");
       
        })
        .catch((err) => {
          alert(err);
        });
    },
  },
}
</script>

<style>
    .gradient-custom-3 {
  /* fallback for old browsers */
  background: #84fab0;

  /* Chrome 10-25, Safari 5.1-6 */
  background: -webkit-linear-gradient(to right, rgba(132, 250, 176, 0.5), rgba(143, 211, 244, 0.5));

  /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  background: linear-gradient(to right, rgba(132, 250, 176, 0.5), rgba(143, 211, 244, 0.5))
}
.gradient-custom-4 {
  /* fallback for old browsers */
  background: #84fab0;

  /* Chrome 10-25, Safari 5.1-6 */
  background: -webkit-linear-gradient(to right, rgba(132, 250, 176, 1), rgba(143, 211, 244, 1));

  /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
  background: linear-gradient(to right, rgba(132, 250, 176, 1), rgba(143, 211, 244, 1))
}
</style>