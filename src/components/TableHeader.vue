<template>
    
    <div >
         <div class="table-header flex vertical" >
            <div v-for="item in weekData" :key='item'>{{item}}</div>
        </div>
         <div class="table-header flex horizontal">
            <div v-for="item in timeData" :key='item'>{{item}}</div>
        </div>
    </div>

</template>

<script>
export default {

data(){
      return{
        weekData:[
            '','понедельник','вторник',"среда","четверг","пятница","суббота",'воскреснье'    
          ],
        timeData:[],
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