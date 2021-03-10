<template>
  <tr > 
        <td 
            v-bind:style="{'background':'purple','border':'2px solid black', width : '10vw' }" 
        >
        {{timeData[ArrayIndex]}}
        </td>
    </tr>
</template>

<script>
export default {
        data(){
            return{
                    timeData:[]
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
}
</script>

<style>



</style>    