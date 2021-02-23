<template>
<div>
  <table v-for="(item,index) in table" :key="index" >
         
        <TableRow  :function="myFunction(item)"/>
        <!-- передаю данные в таблицу-->

  </table>
</div>
</template>  
<script>

import TableRow from './TableRow.vue'

export default {
  
    components:{
        TableRow
    },
    computed:{
        dataTable(items){
          //получения массива 
          return items
          }
      },
    data(){
      return{
        table:[
          [
            {
                id:1,
                text:'my text'
            },{
              id:2,
              text:'new text'
            },{
              id:3,
              text:'mine text'
            },{
                id:3,
              text:'mine text'
            },{
                id:5,
              text:'what about'
            },{
                id:3,
              text:'new one'
            }
          ],[
               {
                id:1,
                text:'my text'
            },{
              id:2,
              text:'new text'
            },{
              id:3,
              text:'mine text'
            },{
                id:3,
              text:'mine text'
            },{
                id:5,
              text:'what about'
            },{
                id:3,
              text:'new one'
            }
            ]
          ],rowCount:4
        //количество строк
        }
      }
}


</script>
<style  scoped>
td,tr{
  border :2px solid black;
  flex-basis: 10%;
  }

  table{
    display: flex;
    flex-wrap: wrap;
    

    }

</style>