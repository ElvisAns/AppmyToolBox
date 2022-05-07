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

            
            <div class="row">
                <button>3</button>
                <button>2</button>
                <button>1</button>
                <button>-</button>
            </div>

            
            <div class="row">
                <button>0</button>
                <button>.</button>
                <button>+/-</button>
                <button>=</button>
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
    width:20vw;
    display: flex;
    justify-content: center;
    flex-direction: column;
}


    .container{
        background-color: rgba(128, 66, 215,.3);
        padding:20px;
    }
   .screen{
       background-color: rgb(255, 255, 255);
       height: 40px;
       width:100%;
   }

   button{
       padding:6px;
       text-align: center;
       margin:5px;
       border-radius: 4px;
       width:calc(20vw/4);
       height: 40px;
   }
   
@media screen and (max-width:800px){
    .container{
        width:80vw;
    }
    button{
       width:calc(80vw/4);
   }

}

   .row{
       display: flex;
       width: auto;
   }
</style>
