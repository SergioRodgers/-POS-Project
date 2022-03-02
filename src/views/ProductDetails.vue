<template>
  <h1>Product Details</h1>
  <div v-if="product" class="product-details">
    <h2>Products</h2>
      <div class="products-container" v-if="product">
          <!-- First card -->
        <div class="card" style="width: 18rem;">
        <img :src="product.image" :alt="product.title" class="card-image-top"/>
        <div class="card-body">
          <h5 class="card-title">{{product.title}}</h5>
          <p class="card-text">Written By: {{ product.author_name }}-</p>
          <p class="card-text">Category: {{product.categories.join(', ')}}</p>
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