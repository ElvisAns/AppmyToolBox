<template>
    <div class="container">
        <div class="screen">
            <div>{{result}}<hr/></div>
            <div class="sm">{{opString}}</div>
        </div>
        <div class="keys">
            <div class="row">
                <button @click="handleButtonsClick('del')" class="r">DEL</button>
                <button @click="handleButtonsClick('%')"  class="a">%</button>
                <button @click="handleButtonsClick('sin')"  class="a">sin</button>
                <button @click="handleButtonsClick('deg')"  class="a">deg</button>
            </div>

            
            <div class="row">
                <button @click="handleButtonsClick('clear')"  class="r">CE</button>
                <button @click="handleButtonsClick('(')" >(</button>
                <button @click="handleButtonsClick(')')" >)</button>
                <button @click="handleButtonsClick('/')" class="o">/</button>
            </div>


            
            <div class="row">
                <button @click="handleButtonsClick('7')" >7</button>
                <button @click="handleButtonsClick('8')" >8</button>
                <button @click="handleButtonsClick('9')" >9</button>
                <button @click="handleButtonsClick('*')" class="o">x</button>
            </div>
            
            <div class="row">
                <button @click="handleButtonsClick('5')" >5</button>
                <button @click="handleButtonsClick('4')">4</button>
                <button @click="handleButtonsClick('3')">3</button>
                <button @click="handleButtonsClick('+')" class="o">+</button>
            </div>

            
            <div class="row">
                <button @click="handleButtonsClick('3')">3</button>
                <button @click="handleButtonsClick('2')">2</button>
                <button @click="handleButtonsClick('1')">1</button>
                <button @click="handleButtonsClick('-')" class="o">-</button>
            </div>

            
            <div class="row">
                <button @click="handleButtonsClick('0')">0</button>
                <button @click="handleButtonsClick('.')">.</button>
                <button @click="handleButtonsClick('-')">+/-</button>
                <button @click="handleButtonsClick('=')" class="e">=</button>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name : "ToolBasicCalculator",
    data(){
        return {
            result:0,
            opString:"",
            history:[]
        }
    },
    methods:{
        handleButtonsClick(val){
            if(val=="="){
                let lastChar = this.opString.substr(this.opString.length,-1);
                if(lastChar == "+" | lastChar == "-" | lastChar == "*" | lastChar == "/"){
                    this.result="#INVALID";
                    this.opString="";
                }
                else{
                    const op = this.opString;
                    const tmp = eval(this.opString);
                    const o = parseFloat(tmp);
                    const l = o.toString();
                    if(l.length>10)
                        this.result=l.substr(0,10);
                    else 
                        this.result=o;
                    this.opString=this.result;
                    this.history.push([op,this.result]);
                    localStorage.history = JSON.stringify(this.history);
                }
            }
            else{
                if(this.opString==""){
                    if(val=="clear"){
                        this.result="0";
                        return;
                    }
                    if(val!=="+" & val!=="/" & val!=="*"){
                        this.opString += String(val);
                    }
                    return;
                }
                
                if(val=="clear"){
                    this.result="0";
                    return;
                }
                if(val=="del"){
                    this.opString=this.opString.slice(0,-1);
                    return;
                }
                this.opString += String(val);
            }
        }
    }
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
       height: 120px;
       width:100%;
       margin:5px 3px 20px;
       padding:1rem;
       border-radius: 2px;
       text-align: right;
       font-size: 2.4em;
       color: antiquewhite;
       display:flex;
       align-items: center;
       justify-content: end;
       font-family: "Montserrat", sans-serif !important;
       flex-direction: column;
   }
   .screen > div{
        width:100%;
        padding-top:-20px;
   }
    hr{
        border-top: 1px solid white;
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
   .sm{
    font-weight: 200;
    font-size:small;
    color:white;
   }
</style>
