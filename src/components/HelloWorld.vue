<template>
<table >
  
        <!-- прохожу по массиву с масивами --> 
        <TableRow   v-for="(item,index) in splitedArray" :key="index" v-bind:oneRowArray="item" :colorizeCellOnMouseOver="colorizeCellOnMouseOver" :colorizeCellOnMouseClick="colorizeCellOnMouseClick" />
        <!-- передаю данные в таблицу к дочерним компонентам-->
        <div  >{{isMouseClicked}}</div>
  
</table>
</template>  
<script>

import TableRow from './TableRow.vue'

export default {
  
    components:{
        TableRow
    },
    methods: {
      
      colorizeCellOnMouseOver() {
        if(this.isMouseClicked){
          console.log('onMouseOver')
        }

      },
       colorizeCellOnMouseClick(){
           console.log('onMouseClick');
         }
    }
    ,
    props:['isMouseClicked'],
    computed:{
        SplitingBaseArray(){
          //функция разделения входного массива  
            let currentArrayIndex=-1;
            //по данному числу будет заполняться массив 
              this.table.forEach((element,index) => {
                  if( index===0 || index % this.rowCount===0){
                    currentArrayIndex++;
                    //перехожу на новый массив
                    this.splitedArray.push([]);
                    //создаю массив в массиве каждый из которых будет отправляться дочерним компонентам
                    this.splitedArray[currentArrayIndex].push(element);
                  }else {
                    this.splitedArray[currentArrayIndex].push(element);
                    //заполняю текущий массив 
                  }
              })
          console.log(this.splitedArray)
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
          
            {
                id:1,
                text:'my text',
                color:'rgba(100,200,200)'
            },{
              id:2,
              text:'new text'
            },{
              id:3,
              text:'mine text'
            },  {
                id:1,
                text:'my text'
            },{
              id:2,
              text:'new text'
            },{
              id:3,
              text:'mine text'
            }
            
          ],rowCount:4
        //количество строк
        ,splitedArray:[]
        }
      }
}


</script>
<style  scoped>


</style>