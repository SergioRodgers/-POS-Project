<template>
    <div class="container not-found">
        <div>
            <marquee class="display-5">The Page You Trying To Access Is Not Found</marquee>
        </div>
        <div class="redirect">
            <router-link to='/' class="display-6">Go To Home Page</router-link>
        </div>
    </div>
</template>
<script>
export default {
    
}
</script>
<style>
    .not-found {
        margin: 200px auto;
        padding: auto;
        color: #c36f09;
    }
    h2 {
        color: #c36f09;
    }
    a {
        
        color: white;
        text-decoration: none;
    }
    .redirect {
        top: 80%;
        left: 40%;
        position: fixed;
    }
</style>