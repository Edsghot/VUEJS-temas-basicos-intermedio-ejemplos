<script setup>
    import { ref } from 'vue';
    const nuevaFruta = ref("");
    
    const agregar=()=>{
        console.log(nuevaFruta.value)
    }

</script>


<template>
    <input type="text" v-model="nuevaFruta">
    <br/>
    <button @click="agregar"> agregar</button>
    <h1>{{ nuevaFruta }}</h1>
</template>