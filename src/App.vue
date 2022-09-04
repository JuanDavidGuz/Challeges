<template>
 <Counter  title="AMBIENTE WED" /><br/>
 <br/> 
 
  <HelloWorld />
  <br/> 
<Indecition/>
 </template>

 <script>
 import Counter from '@/components/Counter.vue';
 import HelloWorld from '@/components/HelloWorld.vue';
 import Indecition from './components/Indecition.vue';
 export default {
  name: 'app',
  components:{
    Counter, 
    HelloWorld,
    Indecition,
}
 }
 </script>
