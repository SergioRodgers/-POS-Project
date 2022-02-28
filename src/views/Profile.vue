<template>
    <div v-if="profile" class="profile">
        <h1>This is a Profile Page</h1>
        <div class="row">
            <div class="col-9 m-auto">
                <div class="card" style="width: ;">
                    <img :src="profile.cover" class="card-img-top" height="400" alt="...">
                    <div class="card-body">
                        <div class="pic">
                             <img id="profile-pic" :src="profile.image" :alt="profile.fullname">
                        </div>
                        <div class="profile-text">
                            <h4 class="profile-title">{{profile.fullname}}</h4>
                            <h4 class="profile-">{{profile.email}}</h4>
                            
                            <p class="joined">Joined: {{profile.join_date}}</p>
                            <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                            <a href="#" class="btn btn-primary">Add Items</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div v-else>Loading...</div>
  
</template>

<script>

export default {
  data() {
    return {
      profile: null,
    };
  },
  
  mounted() {
      if (localStorage.getItem("jwt")) {
        fetch("http://localhost:3200/users/:id", {
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
#profile-pic {
    position: relative;
    top: -150px;
    left: -350px;
    border-radius: 50%;
    border: 5px solid white;
    margin: 10px;
}
.profile-title {
    position: relative;
    display: inline-block;
    top: -150px;
    left: -350px;
    font-weight: bold;
    text-align: left;
    margin: 10px;
}
.profile {
    color: black;
}
</style>