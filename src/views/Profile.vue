<template>
    <div v-if="profile" class="profile">
        <h1>This is a Profile Page</h1>
        <div class="row">
            <div class="col-7 m-auto">
                <div class="card" style="width: 1000px;" >
                    <img :src="profile.cover" class="card-img-top" height="300" alt="...">
                    <div class="card-body" style="height: 500px; text-align:left ">
                        <div class="container">
                            <img id="profile-pic" :src="profile.image" :alt="profile.fullname">
                        
                            <div class="edit-icon d-flex">
                              <i class='fas fa-edit' style='font-size:24px' type="button" data-bs-toggle="modal" data-bs-target="#profileModal"></i>                                
                            </div>
                            <Modal />

                            <div class="profile-text">
                              <h4 class="profile-title">{{profile.fullname}}</h4>
                              <h5 class="profile-">Email: {{profile.email}}</h5>
                              
                              <p class="joined">Joined: {{profile.join_date}}</p>
                              <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                              <button type="button" data-bs-toggle="modal" data-bs-target="#productModal" class="btn btn-primary">Add Products</button>
                              <ModalProduct />
                            </div>
                        </div>
                       
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div v-else>Loading...</div>
  
</template>

<script>
import Modal from '../components/Modal.profile.vue';
import ModalProduct from '../components/Modal.products.vue'
export default {
  data() {
    return {
      profile: null,
    };
  },
  components: {
		Modal,
    ModalProduct
	},
  
  mounted() {
      if (localStorage.getItem("jwt")) {
        fetch("https://balls-united.herokuapp.com/users/:id", {
          method: "GET",
          headers: {
            "Content-type": "application/json; charset=UTF-8",
            Authorization: `Bearer ${localStorage.getItem("jwt")}`,
          },
        }).then(res => res.json())
        .then(data => {
            this.profile = data
            console.log(data)
            
            }).catch((err) => {
            alert("User not logged in");
          });
      }else{
          alert("User not logged in");
        this.$router.push({ name: "Home" });
      }
  }
}
</script>

<style scoped>
#profile-pic, .profile-text {
    position: relative;
    top: -150px;
    
    border-radius: 50%;
    border: 5px solid white;
    margin: 10px; 
}
.profile-title {
    position: relative;
    font-weight: bold;
    text-align: left;
    margin: 10px; 
}
.profile {
    color: black;
}
.edit-icon{
  display: flex;
  flex-direction: row-reverse;
  position: relative;
  top:-200px;
}
</style>