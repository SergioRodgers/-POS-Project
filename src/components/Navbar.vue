<template>
 <nav class="navbar navbar-expand-lg navbar-light bg-muted">
  <div class="container-fluid">
    <a class="navbar-brand" img src="./assets/images/basketball.jpg"></a>
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <form class="d-flex" style="width:50%;">
        <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
        <button class="btn btn-outline-warning" type="submit">Search</button>
      </form>

    <div style="margin-left: 35%">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <router-link class="btn btn-outline-warning" aria-current="page" to="/">Home</router-link>
        </li>
        <li class="nav-item">
          <router-link class="btn btn-outline-warning" to="/about">About</router-link>
        </li>
        </ul>
    </div>
      
    </div>
  </div>
</nav>
</template>


<script>

</script>