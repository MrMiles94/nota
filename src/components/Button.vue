<template>
    <button
    @click="$emit('btn-click')"
      class="btn " 
      :style="{
      backgroundColor:color,
      borderColor:color
      }" 
      :type="btnType"
    >
      {{ text }}
    </button>   
  </template>

<script>
export default {
  name: 'Button',
  props: {
    text: String,
    color: String,
    btnType: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
