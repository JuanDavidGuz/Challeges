<template>
<h1>{{ customTitle }}</h1>
<span> {{counterNumber}}* {{counterNumber}} = {{getMultiplicacion}} </span> <br/>
<button @click="increase">+1</button><br/>
<button @click="decrease">-1</button><br/>
<button @click="reset">reset</button><br/>
</template>

<script>
const valori = 0
export default{
    props:{
        title: String,
        start:{
            type: Number,
            default: 10,
            required: false,
            validador: (value) => {
                return value >= 0
            }
        }
    },
   name: 'Counter',
   data(){
    return{
        counterNumber: valori
    }
   },
   methods :{
    increase(){
        this.counterNumber ++;
    },
    decrease(){
        this.counterNumber --;
    },
    reset(){
        this.counterNumber =  valori
    },
   },
   computed:{
    getMultiplicacion(){
        console.log('calling method')
        return this.counterNumber * this.counterNumber
    },
    customTitle(){
        return this.title || 'counter'
    }
   }
}
</script>

<style scoped>
h1{
    text-align: center;
    font-style: italic;
    color: chartreuse;
}
span{
    font-size: 50px;
    color: rgb(221, 10, 10);
}
button{
     background-color:rgb(10, 35, 220);
     color: rgb(255, 255, 255);
     widows: 300px;
     font-size: 50px;
     font-family: 'Times New Roman',times , serif;
}
</style>
