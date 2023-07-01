<script setup>
import {ref,computed} from 'vue'

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

const classCounter = computed(()=>{
    if(contador.value === 0){
        return 'zero'
    }else if(contador.value>0){
        return 'positive'
    }else{
        return 'negative'
    }
})

</script>

<template>
    <h1>Computed</h1>
    <br/>

    <button @click="increment">Incrementar</button>
    <button @click="decrement">decrementar</button>
    <button @click="reset">reset</button>
    <button :disabled="true">Add</button>
    <br>
    <h1 :class="classCounter">{{ contador }}</h1>


</template>

<style>

.positive{
    color: green;
}
.negative{
    color: red;
}
.zero{
    color:peru;
}
</style>