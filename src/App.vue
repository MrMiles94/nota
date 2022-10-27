<template>
  <div class="container">
    <Header tittle='Task Tracker' />
  </div>
  
</template>

<script>
import Header from './components/Header.vue'

export default {
  name: 'App', 
  components: {
    Header,
  }
} 
</script>

<style>
@import url('http://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
*{
   box-sizing: border-box;
   margin: 0px;
   padding: 0px
}
body{
  font-family: 'Poppins',sans-serif
}
.container{
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
  text-align: center
}
.btn{
  margin: 5px;
  display: inline;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  font-size: 15px;
  text-decoration: none;
  cursor: pointer;
  border-radius: 5px;
  font-family: inherit
}
btn:focus{
  outline: none
}
.btn:active{
  transform:scale(0.98)
}
.btn-block{
  display:block;
  width: 100%
}
</style>
