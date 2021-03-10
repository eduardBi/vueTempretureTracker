<template>
    
   <tr>
            <td v-for="item in weekData" :key="item">{{item.value}}</td>
          </tr>

</template>

<script>
export default {

data(){
      return{
        weekData:[
            {
                value:''
            },
            {
                value:'понедельник'
            },
            {
                value:'вторник'
            },
            {
                value:'среда'
            },
            {
                value:'четверг'
            }
            ,
            {
                value:'пятница'
            },
            {
                value:'суббота'
            },
            {
                value:'воскреснье'
            }   
          ]
        }
    },
    computed:{
            FillTimeTable(){
                //заполняю массив время
                let timeArray=[];
                  for(let i=0;i<24;i++)  {
                      timeArray.push(`${i}:00`)
                  }
                  return timeArray
            }
    },
    mounted(){
        this.timeData=this.FillTimeTable
        console.log(this.timeData)
    }
}
</script>

<style soped>

    .horizontal{
        flex-direction: column;
    }
    .vertical{
        width: 100%;
        justify-content: space-between;
    }
    .vertical>*{
        width: 100%;
    }
    .flex{
        display: flex;
    }
</style>