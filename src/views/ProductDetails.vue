<template>
  <h1>Product Details</h1>
  <div v-if="product" class="product-details">
    <h2>Products</h2>
      <div class="products-container" v-if="product">
          <!-- First card -->
        <div class="card" style="width: 16rem;" >
              
                <img :src="product.image" :alt="product.title" title="More details" class="card-image-top"/>
              
              <div class="card-body">
                <h5 class="card-title">{{product.title}}</h5>
                <p class="card-text">Written By: {{ product.author_name }}-</p>
                <p class="card-text">Category: {{product.categories.join(', ')}}</p>
                <div class="d-flex mb-3">
                <input type="number" class="form-control" value="1" min="1" id="addToCart0">
                <button type="button" class="btn btn-secondary ms-3" onclick="addToCart(0)"><i class="fa fa-shopping-cart"></i></button>
            
                <a href="#" id="edit-but" type="button" class="btn btn"><i class="fa fa-edit" data-bs-toggle="modal" data-bs-target="#editProductModal"></i></a>
                <a href="#" id="del-but" type="button" class="btn btn-remove"><i class="fa fa-trash-o"></i></a>
                <a class="btn btn-danger" @click="deleteProduct">delete</a>
                </div>
              </div>
    </div>
    </div>
  </div>
  <div v-else>Loading products...</div>
</template>

<script>

export default {
  props: ["id"],
  data() {
    return {
      product: null,
    };
  },
  methods: {
    deleteProduct(){
        fetch('https://balls-united.herokuapp.com/products/' + product._id, {
        method: 'DELETE',
        
      }).then(response => response.json()).then(() => 
        {alert("Product deleted");
        this.$router.push({ name: "Dashboard" });
        });
      }
  },
  mounted() {
    if(this.id){
      fetch("https://balls-united.herokuapp.com/products/" + this.id, {
      method: "GET",
      headers: {
        "Content-type": "application/json; charset=UTF-8",
        Authorization: `Bearer ${localStorage.getItem("jwt")}`,
      },
    })
      .then((response) => response.json())
      .then(async (json) => {
        this.product = json;
        console.log(json)
        await fetch(
          "https://balls-united.herokuapp.com/users/" + json.user_id,
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
            console.log(json)
            this.product.author_name = json.fullname;
          });
      });
    }
  },
};
</script>

<style>
.product-details {
  color: black;
}
</style>