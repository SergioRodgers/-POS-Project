<template>
  <div v-if="products" class="container">
    <h2>Products</h2>
      <div class="products-container container" v-if="products">
          <!-- First card -->
          <div class="looping-over" v-for="product of products"
            :key="product._id">
            <div class="card" style="width: 18rem;" >
        <img :src="product.image" :alt="product.title" class="card-image-top"/>
        <div class="card-body">
          <h5 class="card-title">{{product.title}}</h5>
          <p class="card-text">Written By: {{ product.author_name }}-</p>
          <p class="card-text">Category: {{product.categories.join(', ')}}</p>
          <div class="d-flex mb-3">
            <input type="number" class="form-control" value="1" min="1" id="addToCart0">
            <button type="button" class="btn btn-secondary ms-3" onclick="addToCart(0)"><i class="fa fa-shopping-cart"></i></button>
          
            <a href="#" id="edit-but" type="button" class="btn btn" ><i class="fa fa-edit" data-bs-toggle="modal" data-bs-target="#editProductModal"></i></a>
            <a href="#" id="del-but" type="button" class="btn btn-remove"><i class="fa fa-trash-o"></i></a>
            <a class="btn btn-danger" @click="deleteProduct" >delete</a>
          </div>
          <Modal />
        </div>
    </div>
          </div>
        
    </div>
  </div>
  <div v-else>Loading products...</div>
     
</template>

<script>
import Modal from '@/components/Modal.products.edit.vue'
  export default {
    data(){
      return {
        products: null,
      };
    },
    methods:{
      deleteProduct(){
        fetch('https://balls-united.herokuapp.com/products/'+products._id, {
        method: 'DELETE',
      });
      }
    },
    components: { Modal },
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
.products-container {
  display: flex;
  gap: 10px
}



</style>