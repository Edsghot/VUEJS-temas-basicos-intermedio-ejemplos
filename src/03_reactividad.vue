<script setup>
import {ref} from 'vue'

const contador = ref(0);

const increment = ()=>{
    contador.value++;
}
const decrement =()=>{
    contador.value--;
}
const reset = ()=>{
    contador.value = 0;
}

</script>

<template>
    <h1>Reactividad</h1>
    <br/>

    <button @click="increment">Incrementar</button>
    <button @click="decrement">decrementar</button>
    <button @click="reset">reset</button>
    <br>
    <h1 :class="contador>0 ? 'positive' : 'negative'">{{ contador }}</h1>


</template>

<style>

.positive{
    color: green;
}
.negative{
    color: red;
}
</style>