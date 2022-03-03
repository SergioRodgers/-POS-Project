<template>

    <h1>This is a Cart Page</h1>
</template>

<script>
export default {
    data(){
        return{
            products:null
        }
    },

     mounted() {
      if (localStorage.getItem("jwt")) {
        fetch("https://balls-united.herokuapp.com/cart", {
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
                "https://balls-united.herokuapp.com/products/" + product._id,
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
                  product.author_name = json.product_id;
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

<style>


</style>