<template>
    
        <div>dawda</div>
    
</template>  
<script>

export default {
  props: {
    myFunction: { type: Function },
  },
    data(){
      return{
        
        }
      },
      mounted(){
            console.log(this.myFunction)
      }
}

</script>
<style  scoped>


</style>