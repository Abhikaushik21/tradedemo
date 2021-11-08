<template>
<div class="groups">
<select v-model="selected" class="selectinp" >
 <option v-for="val in drop" :value="val" :key="val">
      {{val}}
    </option>
</select>


</div>

</template>

<script>
export default {
    props:['drop'],
    data()
    {
        return{
            selected:""
        }
    }
    
}
</script>

<style scoped>
.groups{
 
  position: relative;
  width:100% ;
}
.selectinp{
     width:  100%;
  padding: 18px 20px;
  font-size: 15px;
  background: white;
  margin: 8px 15px;
  border-radius: 4px;
  box-sizing: border-box;

}


</style>