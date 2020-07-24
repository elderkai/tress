<template>
    <div>
        <input type="text" :value="input" @input="changeInput">
        {{input}}
<div>{{time}}</div>
<div>已经过去了{{overTime}}分钟</div>
    </div>
</template>

<script>
    export default {
        data(){
            return{
                input:"1",
                data:[1,2,3],
                time:"  ",
                second:null,
                overTime:0
            }
        },
        methods:{
        getdata(){
            let theData = new Date();
            let year = theData.getFullYear();
            let month = theData.getMonth()+1;
            let date = theData.getDate();
            let minute = theData.getMinutes();
            let second = theData.getSeconds();
            this.second=second;
            second==0?second="00":null;
            this.time=`${year}/${month}/${date}   ${minute}:${second}`;
        },
        refreshTime(){
            setInterval(() => {
                this.getdata();
            }, 1000);
        },
        changeInput(value,value2){
           if(value.data==null){this.input=""}
           else{
               this.input+=value.data
           }
        }
        },
        created(){
            this.refreshTime();
        },
        watch:{
            second(val){
               if(val==0){
                   this.overTime+=1;
                   this.input=2222;
               }
                
            }
        }
    }
</script>

<style scoped>

</style>