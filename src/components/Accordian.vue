<template>
<div>
    
<button class="accordion" v-on:click="handleAcc">Section 1</button>
<div class='panel' :id="ids.id">{{ids.txt}}</div>
</div>

</template>
<script>

export default{
    name:"accord",
    props:['ids'],
    data()
    {
        return{
            value:"Dkdfjkdf",
        }
    },
    methods:
    {
        handleAcc()
        {
            
           console.log("ids",document.getElementById(this.ids.id).style.display);
        //  let val= document.getElementsByClassName("panel")[0].style.display;
        let val=document.getElementById(this.ids.id).style.display;

          if(val==='block')
          {
              document.getElementById(this.ids.id).style.display='none';

             // document.getElementsByClassName("panel")[0].style.display='none';
          }else
          {
              document.getElementById(this.ids.id).style.display='block';
             // document.getElementsByClassName("panel")[0].style.display='block';
          }

        
        }

    }
}

</script>
<style>
.accordion {
  background-color: #eee;
  color: #444;
  cursor: pointer;
  padding: 18px;
  width: 100%;
  border: none;
  text-align: left;
  outline: none;
  font-size: 15px;
  transition: 0.4s;
}

.active, .accordion:hover {
  background-color: #ccc; 
}

.panel {
  padding: 0 18px;
  display: none;
  background-color: white;
  overflow: hidden;
}


</style>
