<template>
<div  @mousedown=" checkMousePressed(true)"  @mouseup="checkMousePressed(false)" >
      <Table       />
      <div  >{{isMouseClicked}}</div>
      </div>
</template>  
<script>


import Table from './components/HelloWorld.vue'


export default {
  data(){
        return  {isMouseClicked:false}
      },
    components:{
      Table
    },methods:{
        checkMousePressed(pressValue){
          // преверяю зажата ли лкм
          console.log(pressValue)
          this.isMouseClicked=pressValue
          return {}
        }
      }
}

</script>