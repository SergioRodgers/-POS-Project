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

    <div style="margin-left: 25%">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <router-link class="btn btn-outline-warning" aria-current="page" to="/">Home</router-link>
        </li>
        <li class="nav-item">
          <router-link class="btn btn-outline-warning" to="/products">Dashboard</router-link>
        </li>
        <li class="nav-item">
          <router-link class="btn btn-outline-warning" to="/dashboard/cart">Cart</router-link>
        </li>
        <li class="nav-item dropdown">
          <a class=" dropdown-toggle btn btn-outline-warning" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown">
            Me
          </a>
          <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
            <li><router-link class="dropdown-item" :to="{name: 'Profile'}">View Profile</router-link></li>
            <li><router-link class="dropdown-item" :to="{name: 'Profile'}">Delete Account</router-link></li>
            <li><hr class="dropdown-divider"></li>
            <li><router-link @click="logout" class="btn btn-outline-warning" :to="{ name: 'Home' }">Logout</router-link></li>
          </ul>
        </li>
        <li class="nav-item">
          
        </li>
        
        </ul>
    </div>
      
    </div>
  </div>
</nav>
</template>


<script>
  export default {
    data() {
      return {
        isActive: false,
      };
    },
    methods: {
      toggleNav() {
        this.isActive = !this.isActive;
      },
      logout() {
        localStorage.clear();
        this.toggleNav;
      },
    },
  };
</script>
