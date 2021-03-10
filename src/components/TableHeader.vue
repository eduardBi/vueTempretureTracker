<template>
    
   <tr style="background-color: #009879;
    color: #ffffff;">
            <td v-for="(item  ,index) in weekData" :key="index">{{item.value}}</td>
          </tr>

</template>

<script>
export default {

data(){
      return{
        weekData:[
            {
                value:'время'
            },
            {
                value:'пн'
            },
            {
                value:'вт'
            },
            {
                value:'ср'
            },
            {
                value:'чт'
            }
            ,
            {
                value:'пт'
            },
            {
                value:'сб'
            },
            {
                value:'вс'
            }   
          ]
        }
    },
}
</script>

<style soped>

</style>