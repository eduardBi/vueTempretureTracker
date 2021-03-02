<template>
<div  @mousedown=" checkMousePressed(true)"  @mouseup="checkMousePressed(false)" >
      <Table   v-bind:isMouseClicked="isMouseClicked"     />
      <div  >{{isMouseClicked}}</div>
      <input style="border:2px solid black" type="number" @change="setTemperatureValue(temretureValue)" v-model="tempretureValue" >
      </div>
</template>  
<script>


import Table from './components/TableWrapper.vue'




export default {
  data(){
        return  {
            isMouseClicked:false,
            tempretureValue:20
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
          this.temretureValue=temperature
          console.log(temperature)
        },
        computed:{
          
        }
      }
}

</script>