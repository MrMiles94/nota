<template>
    <header>
        <h1>{{tittle}}</h1>
    </header>
</template>
<script>
    export default{
       'name':'Header',
        'tittle':''
    }
</script>
<style scoped>
header{
    display: flex;
    justify-content: space-around  ;
    align-items: center;
    margin-bottom: 20px;
}
</style>