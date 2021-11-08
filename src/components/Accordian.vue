<template>
<div>
    
<button class="accordion" v-on:click="handleAcc">{{ids.name}}</button>
<div class='panel' :id="ids.id">


 <trade-comp v-if="ids.txt==='Trade'"></trade-comp>





</div>

</div>

</template>
<script>
import TradeComp from './TradeComp.vue';

export default{
  components: { TradeComp},
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
        let val=document.getElementById(this.ids.id).style.display;

          if(val==='block')
          {
              document.getElementById(this.ids.id).style.display='none';

          }else
          {
              document.getElementById(this.ids.id).style.display='block';
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
