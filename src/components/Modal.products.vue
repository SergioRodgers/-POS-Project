<template>
  <div class="modal fade" id="productModal" tabindex="-1" aria-labelledby="productModalLabel" aria-hidden="true">
                  <div class="modal-dialog">
                    <div class="modal-content">
                      <div class="modal-header">
                        <h5 class="modal-title text-dark" id="productModalLabel">Add to Products</h5>
                        <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
                      </div>
                      <form @submit.prevent="addProduct">
                      <div class="modal-body">
                        <!-- BODY START -->

                            <div class="form-outline mb-4">
                            <input type="text" id="form3Example1cg" v-model="title" class="form-control form-control-lg" placeholder="product name"/>
                            </div>

                            <div class="form-outline mb-4">
                            <input type="text" id="form3Example3cg" v-model="categories" class="form-control form-control-lg" placeholder="product category"/>
                            </div>

                            <div class="form-outline mb-4">
                            <input type="text" id="form3Example4cdg" v-model="image" class="form-control form-control-lg" placeholder="product picture" />
                            </div>

                            <div class="form-outline mb-4">
                            <input type="text" id="form3Example4cdg" v-model="price" class="form-control form-control-lg" placeholder="price in rands" />
                            </div>

                            <div class="message">
                            <textarea name="message" id="" cols="" v-model="desc" rows="5" style="width: 100%"></textarea>
                            </div>
                     <!-- BODY END -->
                      </div>
                      <div class="modal-footer">
                        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
                        <button type="submit" class="btn btn-primary" data-bs-dismiss="modal">Add</button>
                      </div>
                      </form>
                    </div>
                  </div>
                </div>
</template>

<script>
export default {
    data() {
        return {
            title: null,
            categories: [],
            image: null,
            desc: null,
            price: null,
        }
    },
    methods: {
    addProduct() {
      if (!localStorage.getItem("jwt")) {
        alert("User not logged in");
        return this.$router.push({ name: "Home" });
      }
      fetch("https://balls-united.herokuapp.com/products", {
        method: "POST",
        body: JSON.stringify({
          title: this.title,
          desc: this.desc,
          image: this.image,
          price: parseInt(this.price),
          categories: this.categories
        }),
        headers: {
          "Content-type": "application/json; charset=UTF-8",
          Authorization: `Bearer ${localStorage.getItem("jwt")}`,
        },
      })
        .then((response) => response.json())
        .then((json) => {
          alert("Successfully added a product");
          this.$router.push({ name: "Dashboard" });
        })
        .catch((err) => {
          alert(err);
        });
    },
  },

}
</script>

<style>

</style>