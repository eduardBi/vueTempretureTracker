<template>
<div>
  <table v-for="(item,index) in splitedArray" :key="index" >
         
        <TableRow  v-bind:oneRowArray="item"/>
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
        SplitingBaseArray(){

          //функция разделение входного массива  
           this.table.forEach((element,index) => {
    
              if(index===0 && index % this.rowCount===0){
                console.log('new array created')

              }else if(index){
                console.log('iteration')

              }else{
                console.log('just')
              }
              
          })
          return this.table
             
      }},created(){
         this.SplitingBaseArray
      },
      mounted(){
           
            this.SplitingBaseArray
      }
      ,
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
        ,splitedArray:[]
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