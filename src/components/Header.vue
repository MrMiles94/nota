<template>
  <header>
    <h2>{{ tittle }}</h2>
    <Button @btn-click='$emit("btn-click")' :text="showAddTask ? 'Close':'Add Task'" :color="showAddTask ? 'red':'green'" type="button"/>
  </header>
    
  </template>

<script>
import  Button from './Button'

export default {
  name: 'NavBar',
  props: {
    tittle: String,
    showAddTask:Boolean
  },
  components:{
    Button
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  header{
    display: flex;
    justify-content: space-between;
    align-items: center ;
    margin-bottom: 20px
  }
  h2{
    font-size: x-large
  }
</style>
