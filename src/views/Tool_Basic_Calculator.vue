<template>
    <div class="container">
        <div class="screen"></div>
        <div class="keys">
            <div class="row">
                <button>e</button>
                <button>%</button>
                <button>sin</button>
                <button>deg</button>
            </div>

            
            <div class="row">
                <button>CE</button>
                <button>(</button>
                <button>)</button>
                <button>/</button>
            </div>


            
            <div class="row">
                <button>7</button>
                <button>8</button>
                <button>9</button>
                <button>x</button>
            </div>
            
            <div class="row">
                <button>5</button>
                <button>4</button>
                <button>3</button>
                <button>+</button>
            </div>
        </div>
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

.container{
    background-color: rgb(128, 66, 215);
}
   .screen{
       background-color: rgb(255, 255, 255);
       height: 40px;
       width:100%;
   }
</style>
