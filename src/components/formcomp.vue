<template>

  <form class="formcont">
     <h2>Make an offer..</h2>
   
  <h4>Contact Information</h4>
  *Required
  <br/><br/>

<div class="group">
  <input type="text" class="inputcont" id='firstint' v-model="data.first"/>
  <label for='FirstName' id='first'>FirstName
    <span :style="{color:'red'}">*</span>
  </label>
 
</div>
<div class="group">
  <input type="text" class="inputcont"  v-model="data.last"/>
  <label for='LastName' id='last'>LastName
    <span :style="{color:'red'}">*</span>
  </label>

</div>
<div class="group">

<input type="text" class="inputcont"  v-model="data.email"/>
<label for='Email' id='email'>Email
    <span :style="{color:'red'}">*</span>
  </label>

</div>
 
 <div class="group">
<input type="text" class="inputcont"  v-model="data.phone"/>
<label for='Phone' id='phone'>Phone
    
  </label>


 </div>
  <h4>My Offer</h4>

<div class="group">
    
      <input type="text" class="inputcont" v-model="data.offer"/>
     <label for='Enter Offer' id='offer'>Enter Offer
    <span :style="{color:'red'}">*</span>
  </label>
  

</div>
      
  </form>    

</template>
<script>
export default {
 data()
 {
     return{
         data:{first:"",last:"",email:"",phone:"",offer:""}
     }
 }  
}
</script>

<style scoped>
.formcont{
    padding:0px 25px;
}

label{
 font-size: 15px;
  position: absolute;
  top:35px;
  left:25px;
  z-index: 12;
  transition-delay: ease 0.3s;
}
input:focus ~ label
{
  transform: translateY(-160%);
   font-size: 10px;
    color: grey;
}

.group{
  display: inline-block;
  position: relative;
  margin: 0px 15px;
  width:45% ;
}
.inputcont{
     width:  100%;
  padding: 18px 20px;
  position: relative;
  font-size: 15px;
  margin: 10px 20px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;

}


</style>