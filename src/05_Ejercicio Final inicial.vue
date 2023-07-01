<script setup>
import {ref,computed} from 'vue'

const contador = ref(0);
const arrayFavoritos = ref([])


const increment = ()=>{
    contador.value++;
}
const decrement =()=>{
    contador.value--;
}
const reset = ()=>{
    contador.value = 0;
    arrayFavoritos.value =[]
}

const add = ()=>{
    arrayFavoritos.value.push(contador.value)
}

const bloquearBtnAdd = computed(()=>{
    const numSearch = arrayFavoritos.value.find(num => num === contador.value);

    return numSearch||numSearch === 0;

})


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
    <div class="container text-center mt-3">
    <h1>EJERCICIO FINAL</h1>
    
    <h1 :class="classCounter">{{ contador }}</h1>
    
    <div class="btn btn-group">
    <button @click="increment" class="btn btn-success">Incrementar</button>
    <button @click="decrement" class="btn btn-danger">decrementar</button>
    <button @click="reset" class="btn btn-secondary">reset</button>
    <button @click="add" :disabled="bloquearBtnAdd" class="btn btn-primary">Add</button>
    
    </div>
    
            
    <ul class="list-group mt-3">
        <li
            class="list-group-item"
            v-for="(numero,index) in arrayFavoritos" 
            :key="index"
            
            >
            {{ numero }}
        </li>
    </ul>
    </div>

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