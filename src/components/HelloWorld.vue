<template>
<input type="text" v-model="newMessage " @keypress.enter="addQuote()"/>
{{newMessage}}
<ul>
    <li v-for="(quote, index) in items">
        <span>{{index+1}}, {{quote.mensaje}}</span>
        <span v-if="quote.author"> por {{quote.author}}</span>
        <span v-else>No Author</span>
    </li>
</ul>
</template>


<script>
export default {
data() {
return {
    newMessage:'',
    items: [
        {mensaje: 'Foo',author: 'Juan'},
        {mensaje: 'Bar',author: 'Pedro'}
    ]
}
},
methods: {
    addQuote(){
        this.items.unshift({
            mensaje: this.newMessage,
            
        })
    }
}
}

</script>

<style scoped>
</style>