<template>
<div class="column">
  <div class="row">
    <div class="col-5 landing">
      <div class="left-text">
          <h1>BallersUnited</h1>
    <h2>Join our community of Ballers and get 20% off your first purchase!!</h2> 
      </div>    
    </div>

    <!-- Sign Up From -->
    <div class="col-6 landing right-text">
      <h1 style="margin-left: 50px">Sign Up Here!</h1>

      <!-- Sign Up -->

      <div class="col-md-9 mb-md-0 mb-5" style="padding: auto; margin: auto">
                <form id="contact-form" name="contact-form" action="https://formspree.io/f/xrgjzzoa" target="_blank" method="POST" style="padding-left: 60px;">
                    <!--Grid row-->
                    <div class="row" id="row">
    
                        <!--Grid column-->
                        <div class="col-md-6">
                            <div class="md-form mb-0">
                                <label for="name" class="">Your name</label>
                                <input type="text" id="name" name="Name" class="form-control" style="box-shadow: 0 0.15rem 1.5rem 0 #c36f09;">                            
                            </div>
                        </div>
                        <!--Grid column-->
                        <div class="col-md-6">
                            <div class="md-form mb-0">
                                <label for="lname" class="">Your Last Name</label>
                                <input type="text" id="lname" name="Last Name" class="form-control" style="box-shadow: 0 0.15rem 1.5rem 0 #c36f09;">                           
                            </div>
                        </div>
                        <!--Grid column-->
                        <div class="col-md-6">
                            <div class="md-form mb-0">
                                <label for="email" class="">Your email</label>
                                <input type="text" id="email" name="Email" class="form-control" style="box-shadow: 0 0.15rem 1.5rem #c36f09;">                           
                            </div>
                        </div>             
                    <!--Grid row-->               
                    <div class="col-md-6">
                        <div class="md-form mb-0">
                            <label for="pnum" class="">Your Phone Number</label>
                            <input type="text" id="pnum" name="Cell Number" class="form-control" style="box-shadow: 0 0.15rem 1.5rem 0 #c36f09;">                       
                        </div>
                    </div>
                    <!--Grid row-->
                  
                  <div class="col-md-12">
                    <div class="md-form mb-0">
                        <label for="message" class="">Message</label>
                        <input type="text" id="message" name="Message" class="form-control" style="box-shadow: 0 0.15rem 1.5rem 0 #c36f09;">                       
                    </div>
                </div>
                </div>
                </form>
                <br>
                <div class="text-center text-md-left">
                    <a class="btn btn-warning" onclick="document.getElementById('contact-form').submit();" style="margin-left: 10%; color: black; box-shadow: 0 0.15rem 1.5rem 0 #c36f09;">Submit</a>
                    <a class="btn btn-dark" onclick="document.getElementById('contact-form').reset();" style="margin-left: 4%; color:white; box-shadow: 0 0.15rem 1.5rem 0 #c36f09;">Reset</a>
                </div>
                <div class="status"></div>
            </div>
    </div>
     </div>
</div>

</template>

<script>


export default {
  name: 'Home',
}
</script>

<style>
body {
  overflow: hidden;
}
.landing {
  top: 290px;
  left: 50px;
  position: relative;
  
}
.left-text{
  padding-left: 100px;
  text-align: left;
}

h1{
  color:#c36f09;
  font-weight:bold;
  text-shadow: 3px 3px 3px black;
}
h2{
  color:white;
  text-shadow: 3px 3px 3px black;
}
/* .row {
  width:45%;
  padding-top:20%;
  padding-left:15%;
} */

</style>