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
    <img src="https://i.postimg.cc/k5k9rXjs/Golden-State.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">Golden State Warriors Vest (Home)</h5>
      <p class="card-text">R 299.90</p>
      <div class="d-flex mb-3">
            <input type="number" class="form-control" value="1" min="1" id="addToCart0">
            <button type="button" class="btn btn-secondary ms-3" onclick="addToCart(0)"><i class="fa fa-shopping-cart"></i></button>
          </div>
      <div>
        <a href="#" id="edit-but" type="button" class="btn btn"><i class="fa fa-edit"></i></a>
        <a href="#" id="del-but" type="button" class="btn btn-remove"><i class="fa fa-trash-o"></i></a>
      </div>
    </div>
  </div>
</div>

  
  <!-- Second card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="https://i.postimg.cc/BnBM9hMV/Purp-Lakers.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">LA Lakers Cotton Vest (Purple)</h5>
      <p class="card-text">R 299.90</p>
      <div class="d-flex mb-3">
            <input type="number" class="form-control" value="1" min="1" id="addToCart0">
            <button type="button" class="btn btn-secondary ms-3" onclick="addToCart(0)"><i class="fa fa-shopping-cart"></i></button>
          </div>
      <div>
        <a href="#" id="edit-but" type="button" class="btn btn"><i class="fa fa-edit"></i></a>
        <a href="#" id="del-but" type="button" class="btn btn-remove"><i class="fa fa-trash-o"></i></a>
      </div>
    </div>
  </div>
  </div>

  <!-- Third card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="https://i.postimg.cc/VNSrBvrW/yellowLA.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">LA Lakers Cotton Vest (Yellow)</h5>
      <p class="card-text">R 299.90</p>
      <div class="d-flex mb-3">
            <input type="number" class="form-control" value="1" min="1" id="addToCart0">
            <button type="button" class="btn btn-secondary ms-3" onclick="addToCart(0)"><i class="fa fa-shopping-cart"></i></button>
          </div>
      <div>
        <a href="#" id="edit-but" type="button" class="btn btn"><i class="fa fa-edit"></i></a>
        <a href="#" id="del-but" type="button" class="btn btn-remove"><i class="fa fa-trash-o"></i></a>
      </div>    </div>
  </div>
  </div>

  <!-- 4th card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="https://i.postimg.cc/wTZdRBzp/purp-Shorts.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">LA Lakers Fleece Shorts (Purple)</h5>
      <p class="card-text">R 399.90</p>
      <div class="d-flex mb-3">
            <input type="number" class="form-control" value="1" min="1" id="addToCart0">
            <button type="button" class="btn btn-secondary ms-3" onclick="addToCart(0)"><i class="fa fa-shopping-cart"></i></button>
          </div>
      <div>
        <a href="#" id="edit-but" type="button" class="btn btn"><i class="fa fa-edit"></i></a>
        <a href="#" id="del-but" type="button" class="btn btn-remove"><i class="fa fa-trash-o"></i></a>
      </div>    </div>
  </div>
  </div>

  <!-- 5th card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="https://i.postimg.cc/jdPrNbSn/Warriors-Shorts.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">Golden State Warriors Fleece Shorts</h5>
      <p class="card-text">R 399.90</p>
      <div class="d-flex mb-3">
            <input type="number" class="form-control" value="1" min="1" id="addToCart0">
            <button type="button" class="btn btn-secondary ms-3" onclick="addToCart(0)"><i class="fa fa-shopping-cart"></i></button>
          </div>
      <div>
        <a href="#" id="edit-but" type="button" class="btn btn-edit"><i class="fa fa-edit"></i></a>
        <a href="#" id="del-but" type="button" class="btn btn-remove"><i class="fa fa-trash-o"></i></a>
      </div>
    </div>
  </div>
  </div>
  </div>  


<!-- Second Column -->
<div class="row">
<div class="col">
    <!-- First card -->
    <div class="card" style="width: 18rem;">
    <img src="https://i.postimg.cc/m2JtZR6c/CBball.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">Wilson Chicago Bulls Basketball</h5>
      <p class="card-text">R 499.90</p>
      <div class="d-flex mb-3">
            <input type="number" class="form-control" value="1" min="1" id="addToCart0">
            <button type="button" class="btn btn-secondary ms-3" onclick="addToCart(0)"><i class="fa fa-shopping-cart"></i></button>
          </div>
      <div>
        <a href="#" id="edit-but" type="button" class="btn btn"><i class="fa fa-edit"></i></a>
        <a href="#" id="del-but" type="button" class="btn btn-remove"><i class="fa fa-trash-o"></i></a>
      </div>
    </div>
  </div>
</div>
  
  <!-- Second card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="https://i.postimg.cc/tRd5VvHC/LAball.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">Wilson Los Angeles Lakers Basketball</h5>
      <p class="card-text">R 499.90</p>
     <div class="d-flex mb-3">
            <input type="number" class="form-control" value="1" min="1" id="addToCart0">
            <button type="button" class="btn btn-secondary ms-3" onclick="addToCart(0)"><i class="fa fa-shopping-cart"></i></button>
          </div>
      <div>
        <a href="#" id="edit-but" type="button" class="btn btn"><i class="fa fa-edit"></i></a>
        <a href="#" id="del-but" type="button" class="btn btn-remove"><i class="fa fa-trash-o"></i></a>
      </div>
    </div>
  </div>
  </div>

  <!-- Third card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="https://i.postimg.cc/0y9D196p/1153296-BLUEYELLOW-1-xj-R.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">Wilson Golden State Basketball</h5>
      <p class="card-text">R 499.90</p>
      <div class="d-flex mb-3">
            <input type="number" class="form-control" value="1" min="1" id="addToCart0">
            <button type="button" class="btn btn-secondary ms-3" onclick="addToCart(0)"><i class="fa fa-shopping-cart"></i></button>
          </div>
      <div>
        <a href="#" id="edit-but" type="button" class="btn btn"><i class="fa fa-edit"></i></a>
        <a href="#" id="del-but" type="button" class="btn btn-remove"><i class="fa fa-trash-o"></i></a>
      </div>
    </div>
  </div>
  </div>

  <!-- 4th card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="https://i.postimg.cc/nc4hx77W/headband.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">Jordan Jumpman Basketball Headband</h5>
      <p class="card-text">R 249.90</p>
      <div class="d-flex mb-3">
            <input type="number" class="form-control" value="1" min="1" id="addToCart0">
            <button type="button" class="btn btn-secondary ms-3" onclick="addToCart(0)"><i class="fa fa-shopping-cart"></i></button>
          </div>
      <div>
        <a href="#" id="edit-but" type="button" class="btn btn"><i class="fa fa-edit"></i></a>
        <a href="#" id="del-but" type="button" class="btn btn-remove"><i class="fa fa-trash-o"></i></a>
      </div>
    </div>
  </div>
  </div>

  <!-- 5th card -->
  <div class="col">
  <div class="card" style="width: 18rem;">
    <img src="https://i.postimg.cc/JhDwrVvh/wheadband.jpg" class="card-img-top" alt="">
    <div class="card-body">
      <h5 class="card-title">Jordan Jumpman Basketball Headband</h5>
      <p class="card-text">R 249.90</p>
      <div class="d-flex mb-3">
            <input type="number" class="form-control" value="1" min="1" id="addToCart0">
            <button type="button" class="btn btn-secondary ms-3" onclick="addToCart(0)"><i class="fa fa-shopping-cart"></i></button>
          </div>
      <div>
        <a href="#" id="edit-but" type="button" class="btn btn"><i class="fa fa-edit"></i></a>
        <a href="#" id="del-but" type="button" class="btn btn-remove"><i class="fa fa-trash-o"></i></a>
      </div>
      
    </div>
  </div>
  </div>

  </div>  

    <!-- Pagination -->
</template>

<script>


</script>

<style>
.card {
  margin: auto;
  margin-top:60px;
  color: black;
  height:500px;
}


.form-label{
  color: black;
}
.sort{
  color: rgba(255, 255, 255, 0.784);
}

#del-but{
  color: red;
  height: auto;

}




</style>