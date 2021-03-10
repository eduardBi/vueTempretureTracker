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
                value:'время/день'
            },
            {
                value:'понедельник'
            },
            {
                value:'вторник'
            },
            {
                value:'среда'
            },
            {
                value:'четверг'
            }
            ,
            {
                value:'пятница'
            },
            {
                value:'суббота'
            },
            {
                value:'воскреснье'
            }   
          ]
        }
    },
}
</script>

<style soped>

</style>