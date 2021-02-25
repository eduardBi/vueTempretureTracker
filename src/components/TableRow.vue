<template >
    <tr >
        <td v-for="(singleObject,index) in oneRowArray" v-bind:style="{'background':singleObject.color}" :key="index"   @mouseover="colorizeCellOnMouseOver" @mousedown="colorizeCellOnMouseClick"   >{{singleObject}}</td>
        
    </tr>
    
</template>  
<script>

export default {
    data(){
      return{
          
        }
      },props:['oneRowArray',"isMouseClicked",'colorizeCellOnMouseOver','colorizeCellOnMouseClick'],
}

</script>
<style  scoped>


</style>