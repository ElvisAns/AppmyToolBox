<template>
    <div class="container">
        <div class="screen"></div>
        <div class="keys"></div>
    </div>
</template>

<script>

export default {
    name : "ToolBasicCalculator"
}
</script>

<style scoped>
.container{
    margin:20px auto;
    width:40vw;
    display: flex;
    justify-content: center;
}

@media screen and (max-width:800px){
    .container{
        width:80vw;
    }
}
   .screen{
       background-color: aqua;
       height: 40px;
       width:100%;
   }
</style>
