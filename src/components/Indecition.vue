<template>
<div class="bg-dark"></div>
    <div class="indecision-container">
        <input type="text" v-model="question" placeholder="Hazme una pregunta"/>
        <p>Recuerda finalizar con signo de interrogacion (?)</p>
    </div>
<div>
    <h2>{{question}}</h2>
    <h1>{{answer}}</h1>
    <img :src="imageUrl" />
</div>
</template>
<script>
export default {
    data(){
        return{
            
            question: '',
            answer: null,
            imageUrl: 'https://via.placeholder.com/250'

        }
    },
    methods:{
        async getAnswer(){
            this.answer = 'Pensando....'
            const api = await fetch('https://yesno.wtf/api')
            const data =  await api.json();
            this.answer = data.answer;
            this.imageUrl = data.image
        }

    },
    watch:{
        question(value, oldvalue){
            if(value.includes('?')){
                console.log(value,oldvalue)
                this.getAnswer();
            }
        }
        
    }
}

</script>
<style scoped>
    
</style>