<template>
  <div class="about">
    <h1 style="text-align: center; margin-top: 50px;">Our Products</h1>
  </div>

  <!-- Sort -->

  <div class="container d-flex justify-content-end mb-3 mt-5 pt-4">
      <div class="d-flex w-25 ms-3">
        <div class="sort">Sort by category</div>
        <select
          class="form-select"
          name=""
          id="sortCategory"
          onchange="sortCategory()">
          <option value="All">All</option>
          <option value="Vest">Vest</option>
          <option value="T-Shirt">T-Shirt</option>
          <option value="Top">Top</option>
          <option value="Pants">Pants</option>
          <option value="Other">Other</option>
        </select>
      </div>
      <div class="d-flex w-25 ms-3">
        <div class="sort">Sort name</div>
        <select class="form-select" name="" id="sortName" onchange="sortName()">
          <option value="ascending">Ascending</option>
          <option value="descending">Descending</option>
        </select>
      </div>
      <div class="d-flex w-25 ms-3">
        <div class="sort">Sort price</div>
        <select
          class="form-select"
          name=""
          id="sortPrice"
          onchange="sortPrice()"
        >
          <option value="ascending">Ascending</option>
          <option value="descending">Descending</option>
        </select>
      </div>
    </div>
 
 <!-- First Column   -->
<div class="row">
<div class="col">
    <!-- First card -->
    <div class="card" style="width: 18rem;">
    <img src="../assets/images/GoldenState.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">Golden State Warriors Vest (Home)</h5>
      <p class="card-text">R 299.90</p>
      <a href="#" class="btn btn-primary"> Add to Cart</a>
    </div>
  </div>
</div>

  
  <!-- Second card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="../assets/images/PurpLakers.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">LA Lakers Cotton Vest (Purple)</h5>
      <p class="card-text">R 299.90</p>
      <a href="#" class="btn btn-primary">Add to Cart</a>
    </div>
  </div>
  </div>

  <!-- Third card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="../assets/images/yellowLA.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">LA Lakers Cotton Vest (Yellow)</h5>
      <p class="card-text">R 299.90</p>
      <a href="#" class="btn btn-primary">Add to Cart</a>
    </div>
  </div>
  </div>

  <!-- 4th card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="../assets/images/purpShorts.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">LA Lakers Fleece Shorts (Purple)</h5>
      <p class="card-text">R 399.90</p>
      <a href="#" class="btn btn-primary">Add to Cart</a>
    </div>
  </div>
  </div>

  <!-- 5th card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="../assets/images/WarriorsShorts.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">Golden State Warriors Fleece Shorts</h5>
      <p class="card-text">R 399.90</p>
      <a href="#" class="btn btn-primary">Add to Cart</a>
    </div>
  </div>
  </div>
  </div>  


<!-- Second Column -->
<div class="row">
<div class="col">
    <!-- First card -->
    <div class="card" style="width: 18rem;">
    <img src="../assets/images/CBball.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">Wilson Chicago Bulls Basketball</h5>
      <p class="card-text">R 499.90</p>
      <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>
</div>
  
  <!-- Second card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">Card Head</h5>
      <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
      <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>
  </div>

  <!-- Third card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">Card Head</h5>
      <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
      <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>
  </div>

  <!-- 4th card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">Card Head</h5>
      <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
      <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>
  </div>

  <!-- 5th card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">Card Head</h5>
      <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
      <a href="#" class="btn btn-primary">Go somewhere</a>
    </div>
  </div>
  </div>

  </div>  


     
</template>

<script>
// Sort Function
let products = JSON.parse(localStorage.getItem("products"))
  ? JSON.parse(localStorage.getItem("products"))
  : [
      {
        title: "Golden State Warriors Vest (Home)",
        category: "Vest",
        price: 299.90,
      },
      {
        title: "Naruto Uzumaki Sweats",
        category: "Pants",
        price: 349.99,
        img: "https://litb-cgis.rightinthebox.com/images/640x640/202201/bps/product/inc/hvbxpy1641365761840.jpg?fmt=webp&v=1",
      },
      {
        title: "Itachi Uchiha Hoodie",
        category: "Hoodie",
        price: 399.99,
        img: "https://litb-cgis.rightinthebox.com/images/640x640/202111/bps/product/inc/jrgnbe1637223954950.jpg?fmt=webp&v=1",
      },
      {
        title: "Itachi Uchiha Black Hoodie",
        category: "Hoodie",
        price: 399.99,
        img: "https://litb-cgis.rightinthebox.com/images/640x640/202109/bps/product/inc/jyhgbq1632378296164.jpg?fmt=webp&v=1",
      },
    ];


</script>

<style>
.card {
  margin: auto;
  margin-top:60px;
  color: black;
}

.form-label{
  color: black;
}
.sort{
  color: white;
}



</style>