<template>
    <div class="group">
  <input type="text" class="inputcont" id='firstint' v-model="val"/>
  <label :for="labeldata" id='first'>{{labeldata}}
    <span :style="{color:'red'}">*</span>
  </label>
 
</div>
</template>
<script>
export default {
    props:['labeldata'],
    data()
    {
        return{
val:"",
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
  margin: 0px 0px;
  width:100% ;
}
.inputcont{
     width:  100%;
  padding: 18px 20px;
  position: relative;
  font-size: 15px;
  margin: 10px 15px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;

}
</style>