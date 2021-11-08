<template>
<div class="tradecomp">
    <div class="row1">
     <div class="col12">
         <button class="tbtn" id='notrade' v-on:click="handleClick('notrade')">No Trade in</button>
   
     
         <button class="tbtn" id='yestrade' v-on:click="handleClick('yestrade')" >Yes, I have a Trade-in</button>
     
    </div>
  
      </div>
      <!-------Option view------->
 <div class="row2" v-if="yestrade">
        <div class="innercol6">
            <dropdowns :drop="yearopt"/>
            
        </div>
          <div class="innercol6">
               <InputField :labeldata="label1"/>
            
        </div>
        <div class="innercol6">
               <InputField :labeldata="label2"/>
            
        </div>
         <div class="innercol6">
               <dropdowns :drop="conditionopt"/>
            
        </div>
        <div class="innercol6">
               <InputField :labeldata="label3"/>
            
        </div>
         <div class="innercol6">
               <InputField :labeldata="label4"/>
            
        </div>
       <div class="col12">
           <hr/>
       </div>
    </div>

</div>
    
</template>
<script>
import Dropdowns from './Dropdowns.vue';
import InputField from './inputField.vue';

export default {
  components: { Dropdowns,InputField },
  
    data()
 
      {
        return{
            yearopt:['select year','2021','2020','2019','2018','2017','2016','2015','2014','2013','2012','2011','2010'],
            label1:"Make",
            label2:"Model",
            yestrade:false,

            label3:"Estimated Mileage",
            label4:"VIN",
            conditionopt:['Excellent','Good','Fair','Poor'],
            

        }
    },
    methods:{
        handleClick(id)
        {
           var idata= document.getElementById(id).className;
         if(idata==='tbtn')
         {
             if(id=='notrade')
             {
  document.getElementById(id).className='active';
  this.yestrade=false;
  document.getElementById('yestrade').className='tbtn';
             }else
             {
               document.getElementById(id).className='active';
               this.yestrade=true;
  document.getElementById('notrade').className='tbtn';  
             }
           

         }
        }
    }
    
}
</script>
<style scoped>

.tradecomp{
    display: flex;
    flex-wrap: wrap;
     padding: 0px 20px;
   
    width:100%;
    justify-content: flex-start;
}
.row1{   
    display: inline-flex;
    flex-wrap: wrap;
    padding: 0px 25px;
    width: 100%;
    
}
.row2{   
    display: inline-flex;
    flex-wrap: wrap;
    width: 100%;
    
}

.col6{
    
    width:50%;
}
.innercol6{

width: 45%;
margin:0px 5px;
}
.col12{
    width: 100%;
}
.tbtn,.active{
     width: 30%;
    cursor: pointer;
    margin-top:15px;
    margin-bottom: 15px;
    
    padding:15px;
    
}
.tbtn{
background:white;
}

.active{
     background: #b5251920;
      border:solid #b52519;
}
</style>