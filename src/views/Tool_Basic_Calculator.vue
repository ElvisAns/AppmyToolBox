<template>
    <div class="container">
        <div class="screen">909</div>
        <div class="keys">
            <div class="row">
                <button class="a">e</button>
                <button class="a">%</button>
                <button class="a">sin</button>
                <button class="a">deg</button>
            </div>

            
            <div class="row">
                <button class="r">CE</button>
                <button>(</button>
                <button>)</button>
                <button class="o">/</button>
            </div>


            
            <div class="row">
                <button>7</button>
                <button>8</button>
                <button>9</button>
                <button class="o">x</button>
            </div>
            
            <div class="row">
                <button>5</button>
                <button>4</button>
                <button>3</button>
                <button class="o">+</button>
            </div>

            
            <div class="row">
                <button>3</button>
                <button>2</button>
                <button>1</button>
                <button class="o">-</button>
            </div>

            
            <div class="row">
                <button>0</button>
                <button>.</button>
                <button>+/-</button>
                <button class="e">=</button>
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
        background-color: rgba(143, 132, 221, 0.535);
        padding:20px;
        border-radius: 10px;
    }
   .screen{
       background-color: blue;
       height: 80px;
       width:100%;
       margin:5px 3px 20px;
       padding:3px;
       border-radius: 2px;
   }

   button{
       padding:6px;
       text-align: center;
       margin:5px;
       border-radius: 12px;
       width:calc(20vw/4);
       height: 40px;
       box-shadow: 3px 6px #bdcdec;
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
   button.a{
       background-color:blue;
       color:white;
   }
   button.r{
       background-color: rgb(255, 7, 32);
       color:white;
   }
   button.o{
       
       background-color: rgb(255, 166, 0);
       color:white;
   }
   button.e{
       background-color: green;
       color: white;
   }
   button{
       color:white;
       background-color:rgb(106, 106, 234);
   }
</style>
