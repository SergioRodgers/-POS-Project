<template>
    <!-- Modal -->
                <div class="modal fade" id="profileModal" tabindex="-1" aria-labelledby="profileModalLabel" aria-hidden="true">
                  <div class="modal-dialog">
                    <div class="modal-content">
                      <div class="modal-header">
                        <h5 class="modal-title text-dark" id="profileModalLabel">Edit Profile</h5>
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

                            <div class="form-outline mb-4">
                            <input type="text" id="form3Example4cdg" v-model="profile" class="form-control form-control-lg" placeholder="profile picture" />
                            </div>

                            <div class="form-outline mb-4">
                            <input type="text" id="form3Example4cdg" v-model="cover" class="form-control form-control-lg" placeholder="cover photo" />
                            </div>

                            <div class="message">
                            <textarea name="message" id="" cols="" v-model="message" rows="5" style="width: 100%"></textarea>
                            </div>
                     <!-- BODY END -->
                      </div>
                      <div class="modal-footer">
                        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                        <button type="submit" class="btn btn-primary" data-bs-dismiss="modal">Save Changes</button>
                      </div>
                      </form>
                    </div>
                  </div>
                </div>
</template>

<script>
export default {
  props: ["id"],
    data() {
        return {
            profile:"",
            cover:"",
            message:"",
            contact:"",
            

        }
    },
    methods: {
      editProfile(){
        fetch('https://balls-united.herokuapp.com/users/:id', {
          method: 'PUT',
          body: JSON.stringify({
            image: this.profile,
            cover: this.cover,
            message: this.message,
          }),
          headers: {
            'Content-type': 'application/json; charset=UTF-8',
             Authorization: `Bearer ${localStorage.getItem("jwt")}`,
          },
        })
        .then((response) => response.json())
        .then((json) => console.log(json));
      }
    }
    
}
</script>

<style>

</style>