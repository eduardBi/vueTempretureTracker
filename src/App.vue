<template>
<div  @mousedown=" checkMousePressed(true)"  @mouseup="checkMousePressed(false)" >
      <Table   v-bind:isMouseClicked="isMouseClicked"     />
      <div  >{{isMouseClicked}}</div>
      <InputValue  v-bind:setTemperatureValue="setTemperatureValue"/>
      </div>
</template>  
<script>


import Table from './components/TableWrapper.vue'
import InputValue from './components/InputValue'



export default {
  data(){
        return  {isMouseClicked:false}
      },
    components:{
      Table,InputValue
    },methods:{
        checkMousePressed(pressValue){
          // преверяю зажата ли лкм
          console.log(pressValue)
          this.isMouseClicked=pressValue
          return {}
        },
        setTemperatureValue(temperatue){
          console.log(temperatue)
        }
      }
}

</script>