<template>
<div  @mousedown=" checkMousePressed(true)"  @mouseup="checkMousePressed(false)" >
      <Table  
         v-bind:isMouseClicked="isMouseClicked"
         v-bind:temretureMax="temretureMax"   
      />
      <div>{{isMouseClicked}}</div>
      <input style="border:2px solid black" 
        type="number" 
        @change="setTemperatureValueMax(temretureMax)" 
        v-model="temretureMax"  
      >
      </div>
</template>  
<script>


import Table from './components/TableWrapper.vue'


export default {
  data(){
        return  {
            isMouseClicked:false,
            temretureMax:20
        }
      },
    components:{
      Table
    },methods:{
        checkMousePressed(pressValue){
          // преверяю зажата ли лкм
          console.log(pressValue)
          this.isMouseClicked=pressValue
        },
        setTemperatureValueMax(temperature){
          //максимальное значение влияет только на закрашивание  
          this.temretureMax=temperature
        },
      }
}

</script>

<style >

    td{
      cursor: pointer;
      -webkit-touch-callout: none;
      -webkit-user-select: none;
      -khtml-user-select: none;
      -moz-user-select: none;
      -ms-user-select: none;
      user-select: none;
      
    }

    :root{
      color: #ffffff
    }

    table{
        border-collapse:collapse;
    }
    
    td{
      border: 2px solid white;
      text-indent: 10px;
      line-height: 1.5em;
    }



</style>