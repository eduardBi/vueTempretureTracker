<template >
    <tr > 
    <td 
        style="background-color: #009879"
    >
      {{timeData[ArrayIndex]}}
    </td>
      
        <td 
            class="table-wrapper-item"
            v-for="(singleObject,index) in oneRowArray"
            v-bind:style="{'background':singleObject.color ,width:'15vw'}" 
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
             timeData:[],
        }
      },
       computed:{
            FillTimeTable(){
                //заполняю массив время
                let timeArray=[];
                  for(let i=0;i<24;i++)  {
                      timeArray.push(`${i}:00`)
                  }
                  return timeArray
            }
    }
      ,
        mounted(){
        this.timeData=this.FillTimeTable
        console.log(this.timeData)
    },
        props:['oneRowArray',"isMouseClicked",'colorizeCellOnMouseOver','colorizeCellOnMouseClick','ArrayIndex'],
}

</script>
<style  scoped>
    
    td{
      border: 2px solid white;
    }

  
</style>