<template >
    <tr >
        <td v-for="(singleObject,index) in oneRowArray" v-bind:style="{'background':singleObject.color}" :key="index"   @mouseover="colorizeCellOnMouseOver(ArrayIndex,singleObject)" @mousedown="colorizeCellOnMouseClick(ArrayIndex,singleObject)"   >{{singleObject}}</td>
        
    </tr>
    
</template>  
<script>

export default {
    data(){
      return {
            
        }
      },
       mounted(){
          console.log(this.ArrayIndex)
        },
        props:['oneRowArray',"isMouseClicked",'colorizeCellOnMouseOver','colorizeCellOnMouseClick','ArrayIndex'],
}

</script>
<style  scoped>


</style>