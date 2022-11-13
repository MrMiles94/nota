<template>
  <div class="container">
    <NavBar @btn-click="showAddTask" 
    tittle="Task Tracker"
    :showAddTask="showTask"
    />
    <AddTask v-show="showTask" @add-task='addTask'/>
    <Tasks 
      @toggle-reminder='toggleReminder'
      @delete-task="deleteTask"
      :tasks='tasks'
    />
    <router-view></router-view>
    <Footer/>
  </div>
  
</template>

<script>
import NavBar from './components/Header'
import Footer from './components/Footer'
import Tasks from './components/Tasks'
import AddTask from './components/AddTask'

export default {
  name: 'App',
  components: {
    NavBar,
    Tasks,
    AddTask,
    Footer,
  },
  data(){
    return {
      tasks:[],
      showTask:false
    }  
  },
  methods:{
    deleteTask(id){
      if(confirm('Are you sure?')){
        this.tasks = this.tasks.filter( (task)=>task.id !== id )
      }
      
    },
    toggleReminder(id){
      this.tasks = this.tasks.map(
        (task)=> task.id === id ? {...task, reminder: !task.reminder}: task 
      )
    },
    addTask(task){
      this.tasks.unshift(task)
      this.showTask = !this.showTask
    },
    showAddTask(){
      this.showTask = !this.showTask
    }
  },
  created(){
    this.tasks = [
      {
        id:1,
        text:'Doctors Appointment',
        day: 'March 1st at 2:30pm',
        reminder:true,
      },
      {
        id:2,
        text:'Meeting at School',
        day: 'March 3rd at 1:30pm',
        reminder:true,
      },
      {
        id:3,
        text:'Food shopping',
        day: 'March 1st at 11:30pm',
        reminder:false,
      }
    ]
  }
}
</script>

<style>
@import url("http://googleapis.com/css2?family=Poppins:wght@300;400&display=swap");
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.container{
  text-align: left;
    MAX-width: 500PX;
    margin: 30PX AUTO;
    overflow: auto;
    min-height: 200px;
    height: auto;
    border: 1px solid steelblue;
    padding:30px;
    border-radius: 5px
  }
  .btn{
    display: inline-block;
    background-color: #000;
    color: #fff;
    border: none;
    padding: 10px 20px;
    margin: 5px;
    border-radius: 5px;
    cursor: pointer;
    text-decoration: none;
    font-size: 15px;
    font-family: inherit;
  }
  .btn:focus{
    outline: none; 
  }
  .btn:active{
    transform: scale(0.98);
  }
  .btn-block{
    display: block;
    width: 100%;
  }
</style>
