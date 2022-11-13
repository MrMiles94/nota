<template>
<div 
    :class="task.reminder ? 'task reminder' : 'task'">
    <h4>{{task.text }} 
        <i @click="$emit('delete-task',task.id)" class="fas fa-times"></i>
    </h4>
    <p>{{task.day}}</p>
</div>
    
</template>
<script>
    export default {
        name:'Task',
        props:{
            task: Object,
        },
        methods:{
        }
    }
</script>
<style scope>
    .task{
        background:#f4f4f4;
        margin: 5px;
        padding: 10px 20px;
        cursor: pointer;
        border-radius: 10px 0px 10px 0px;
    }
    .fas.fa-times{
        color: red;
    }
    .task.reminder{
        border-left:8px solid green;
    }
    .task h4{
        display: flex;
        align-items: center;
        justify-content: space-between  
    }
</style>