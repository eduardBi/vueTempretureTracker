<template>
<table >
  
        <!-- прохожу по массиву с масивами --> 
        <TableRow   v-for="(item,index) in splitedArray" :key="index" v-bind:oneRowArray="item"  :ArrayIndex="index" :colorizeCellOnMouseOver="colorizeCellOnMouseOver" :colorizeCellOnMouseClick="colorizeCellOnMouseClick" />
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
      colorizeCellOnMouseOver(ArrayIndex,itemID,singleObject) {
        //закрашивает при наведении зажатой кнопки мыши

          let createColor=(colorValue)=>{
            //let thirdPart=colorValue/3
            console.log(colorValue)
            //нахожу треть от максимального числа 
             /* if(){

              }else if(){
              
              }else if(){

              }*/

            

          }

        if(this.isMouseClicked){
          //если пкм зажата прохожу циклом по массиву 
             this.splitedArray[ArrayIndex].splice(itemID,1,{...singleObject,color:'rgb(200,200,200)'})
             
        }
        
      },
       colorizeCellOnMouseClick(ArrayIndex,itemID,singleObject){
         //закрашивает при клике на элемент
           this.splitedArray[ArrayIndex].splice(itemID,1,{...singleObject,color:'rgb(200,200,200)'})
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
             
      }
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
                text:'my text',
                color:'rgba(100,200,200)'
            },{
              id:2,
              text:'new text'
            },{
              id:3,
              text:'mine text'
            }, {
                id:1,
                text:'my text',
                color:'rgba(100,200,200)'
            },{
              id:2,
              text:'new text'
            },{
              id:3,
              text:'mine text'
            }, {
                id:1,
                text:'my text',
                color:'rgba(100,200,200)'
            },{
              id:2,
              text:'new text'
            },{
              id:3,
              text:'mine text'
            } ,{
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