<template>
    <form action="">
        <label for=""></label>
        <input type="number" @change="setTemperatureValue(temretureValue.tempreture)"  v-model="temretureValue.tempreture">
    </form>
</template>

<script>
export default {
  data() {
     return {
        temretureValue:{tempreture:20}
      }
    },
      props:['setTemperatureValue'],
    methods:{
        
    },
}

</script>

<style>

</style>