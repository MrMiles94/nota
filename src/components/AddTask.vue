<template>
    <form @submit.prevent="onSubmit" class="add-form" >
        <div class="form-control">
            <label for="task">Task</label>
            <input v-model="text" id="task" type="text">
        </div>
        <div class="form-control">
            <label for="day-time">Day & Time </label>
            <input v-model="day" id="day-time" type="date">
        </div>
        <div class="form-control form-control-check">
            <label for="day-time">Set Reminder </label>
            <input v-model="reminder" id="day-time" type="checkbox">
        </div>
        <input  type="submit" value="Save Task" class="btn">
    </form>
</template>
<script>
    export default {
        name:"AddTask",
        data(){
            return{
                text:'',
                day:'',
                reminder:false
            }
        },
        methods:{
            onSubmit(){
                if(!this.text || !this.day){
                    alert('Come on, Check your Inputs Agian!')
                    return
                }
                const newTask = {
                    id:Math.floor(Math.random()*1000000),
                    text:this.text,
                    day:this.day,
                    reminder:this.reminder
                }
                this.$emit('add-task',newTask)

                this.text=""
                this.day=""
                this.reminder=false
            }
        }
    }
</script>
<style>
*{
    transition-duration: 300ms
}
    input{
        padding: 8px
    }
    .add-form{
        width: 100%;
        min-height: 50px;
        display: flex;
        flex-direction: column;
        margin-bottom: 40px
    }
    .form-control{
        width: 100%;
        display: flex;
        flex-direction: column;
        margin-bottom: 20px;
    }
    .form-control-check{
        flex-direction: row !important;
    }
    .form-control-check>input{
        margin-left: 40%
    }
</style>
