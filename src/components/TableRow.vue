<template >
    <tr >
        <td v-for="(singleObject,index) in oneRowArray" v-bind:style="{'background':singleObject.color}" :key="index">{{singleObject}}</td>
    </tr>
    
</template>  
<script>

export default {
    data(){
      return{
        
        }
      },props:['oneRowArray'],
      mounted(){
            
      }
}

</script>
<style  scoped>


</style>