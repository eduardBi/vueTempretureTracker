<template>
<div  @mousedown=" checkMousePressed(true)"  @mouseup="checkMousePressed(false)" >
      <Table   v-bind:isMouseClicked="isMouseClicked"  v-bind:temretureMax="temretureMax"   />
      <div  >{{isMouseClicked}}</div>
      <input style="border:2px solid black" type="number" @change="setTemperatureValueMax(temretureMax)" v-model="temretureMax"  >
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