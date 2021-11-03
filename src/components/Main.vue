<template>
<div class='flex-container'>
<button class='btn' v-on:click="handleModal">Make an offer</button>

<div class='modal' ref="mymodal"><div class='modal-content'>
    <p>Make an offer..</p>
    <button :style="{float:'right'}" v-on:click="handleModal">X</button>
    <accordion :ids="accrd"/>
     <accordion :ids='accrd1'/>
     

</div>
</div>
</div>
</template>

<script>
import accordion from "./Accordian.vue"
export default {
  name: 'maincomp',
  components:{accordion},data()
  {
      return{
          accrd:{id:'a1',txt:"Section 1 desc"},
          accrd1:{id:'a2',txt:'Section 2 desc'},
          
      }
  },
  methods:{
      handleModal()
      {
          let val=this.$refs.mymodal.style.display;
          if(!val)
          {
this.$refs.mymodal.style.display='block'
          }else
          {
          
          this.$refs.mymodal.style.display=val==='none'?'block':'none';
          }
      }
  }

}

</script>

<style>
.flex-container{
    display:flex;
    justify-content:center;
    align-items:center;

}
.btn{
    background:yellow;
    cursor:pointer;
}

.modal {
  display: none; 
  position: fixed; 
  z-index: 1; 
  padding-top: 100px; 
  left: 0;
  top: 0;
  width: 100%; 
  height: 100%; 
  overflow: auto; 
  background-color: rgb(0,0,0); 
  background-color: rgba(0,0,0,0.4); 
}
.modal-content {
  position: relative;
  background-color: white;
  margin: auto;
  padding: 0;
  border: 1px solid #888;
  width: 65%;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2),0 6px 20px 0 rgba(0,0,0,0.19);
  animation-name: animatetop;
  animation-duration: 0.4s
}


</style>


