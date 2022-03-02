<template>
  <div v-if="products">
    <h2>Products</h2>
      <div class="products-container" v-if="products">
          <!-- First card -->
        <div class="card" style="width: 18rem;" v-for="product of products"
            :key="product._id">
        <!-- <img :src="product.image" :alt="product.title" class="card-image-top"/> -->
        <div class="card-body">
          <h5 class="card-title">{{product.title}}</h5>
          <p class="card-text">Written By: {{ product.author_name }}-</p>
          <p class="card-text">Category: {{product.categories.join(', ')}}</p>
          <router-link :to="{ name: 'ProductDetails', params: { id: product._id } }" class="btn btn-primary">more</router-link>
        </div>
    </div>
    </div>
  </div>
  <div v-else>Loading products...</div>
     
</template>

<script>
  export default {
    data(){
      return {
        products: null,
      };
    },
    
    mounted() {
      if (localStorage.getItem("jwt")) {
        fetch("https://balls-united.herokuapp.com/products", {
          method: "GET",
          headers: {
            "Content-type": "application/json; charset=UTF-8",
            Authorization: `Bearer ${localStorage.getItem("jwt")}`,
          },
        })
          .then((response) => response.json())
          .then((json) => {
            this.products = json;
            console.log(json)
            this.products.forEach(async (product) => {
              await fetch(
                "https://balls-united.herokuapp.com/users/" + product.user_id,
                {
                  method: "GET",
                  headers: {
                    "Content-type": "application/json; charset=UTF-8",
                    Authorization: `Bearer ${localStorage.getItem("jwt")}`,
                  },
                }
              )
                .then((response) => response.json())
                .then((json) => {
                  product.author_name = json.fullname;
                });
            });
          })
          .catch((err) => {
            alert("User not logged in");
          });
      } else {
        alert("User not logged in");
        this.$router.push({ name: "Home" });
      }
    },
  }
</script>

<style scoped>
.card {
  margin: auto;
  margin-top:60px;
  color: black;
}




</style>