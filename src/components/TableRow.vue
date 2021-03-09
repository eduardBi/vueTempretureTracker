<template >
    <tr >
        <td 
            v-for="(singleObject,index) in oneRowArray" 
            v-bind:style="{'background':singleObject.color}" 
            :key="index"    
            @mouseover="colorizeCellOnMouseOver(ArrayIndex,index,singleObject)" 
            @mousedown="colorizeCellOnMouseClick(ArrayIndex,index,singleObject)"   
            >{{singleObject.value}}
        </td>
        
    </tr>
    
</template>  
<script>

export default {
    data(){
      return {
            
        }
      },
       mounted(){
        },
        props:['oneRowArray',"isMouseClicked",'colorizeCellOnMouseOver','colorizeCellOnMouseClick','ArrayIndex'],
}

</script>
<style  scoped>


</style>