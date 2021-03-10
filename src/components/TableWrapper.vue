<template>
<div class="table-wrapper-relative">


    <table  >
            <!-- прохожу по массиву с масивами -->
            <TableHeader></TableHeader>
            <TableRow   
                v-for="(item,index) in splitedArray" 
                :key="index" v-bind:oneRowArray="item"  
                :ArrayIndex="index" 
                :colorizeCellOnMouseOver="colorizeCellOnMouseOver" 
                :colorizeCellOnMouseClick="colorizeCellOnMouseClick"  
            />
            <!-- передаю данные в таблицу к дочерним компонентам-->
            <div  >{{isMouseClicked}}</div>
      
    </table>
</div>
</template>  
<script>

import TableRow from './TableRow.vue'
import TableHeader from './TableHeader.vue'

export default {
  
    components:{
        TableRow,TableHeader
    },
    methods: {
      colorizeCellOnMouseOver(ArrayIndex,itemID,singleObject) {
        //закрашивает при наведении зажатой кнопки мыши

        if(this.isMouseClicked){
          //если пкм зажата прохожу циклом по массиву 
             this.splitedArray[ArrayIndex].splice(itemID,1,{...singleObject,color:this.createColor(this.temretureMax),value:this.temretureMax})
             
        }
        
      },
       colorizeCellOnMouseClick(ArrayIndex,itemID,singleObject){
         //закрашивает при клике на элемент
           this.splitedArray[ArrayIndex].splice(itemID,1,{...singleObject,color:this.createColor(this.temretureMax),value:this.temretureMax})
         },
        createColor(value){
        let specializedColor=value*2
              if(this.temretureMax>50 &&  this.temretureMax<100){
                  return `rgb(250,${specializedColor},${specializedColor})`
              }else if(this.temretureMax<50){
                  return `rgb(100,${specializedColor},100)`
              }else if(this.temretureMax>100){
                  return `rgb(255,${specializedColor},100)`
              }
              return ''
          }
    }
    ,
    props:['isMouseClicked','temretureMax'],
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
                    this.splitedArray[currentArrayIndex].push({value:element,color:this.createColor(element)});
                  }else {
                    this.splitedArray[currentArrayIndex].push({value:element,color:this.createColor(element)});
                    //заполняю текущий массив 
                  }
              })
          console.log(this.splitedArray)
          return this.table
             
      }
      },
      mounted(){
          for(let i=0;i<140;i++){
              this.table.push(this.temretureMax);
          }
          this.SplitingBaseArray

        }
      ,
    data(){
      return{
        table:[
            
          ],rowCount:7
        //количество строк
        ,splitedArray:[],
        }

    }
}


</script>
<style  scoped>

  .table-wrapper-relative{
    position: relative;
  }

</style>