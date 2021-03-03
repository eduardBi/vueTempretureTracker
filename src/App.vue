<template>
<div  @mousedown=" checkMousePressed(true)"  @mouseup="checkMousePressed(false)" >
      <Table   v-bind:isMouseClicked="isMouseClicked"     />
      <div  >{{isMouseClicked}}</div>
      <input style="border:2px solid black" type="number" @change="setTemperatureValue(temretureValue)" v-model="tempretureValue" >

      <input style="border:2px solid black" type="number" @change="setTemperatureValueMax(temretureMax)" v-model="temretureMax"  >
      </div>
</template>  
<script>


import Table from './components/TableWrapper.vue'




export default {
  data(){
        return  {
            isMouseClicked:false,
            tempretureValue:20,
            temretureMax:100
        }
      },
    components:{
      Table
    },methods:{
        checkMousePressed(pressValue){
          // преверяю зажата ли лкм
          console.log(pressValue)
          this.isMouseClicked=pressValue
          return {}
        },
        setTemperatureValue(temperature){
          //заполнаяемое значение в таблице 
          this.temretureValue=temperature
          console.log(temperature)
        },
        setTemperatureValueMax(temperature){
          //максимальное значение влияет только на температуру 
          this.temretureMax=temperature
          console.log(this.temretureMax)
        },
        computed:{
          
        }
      }
}

</script>