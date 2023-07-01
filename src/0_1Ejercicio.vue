<script setup>
const arrayFrutas = [
    {
        name: "manzana",
        price: "$2.00",
        description: "una manzana",
        stock: 5, 
    },
    {
        name: "Pera",
        price: "$2.00",
        description: "una pera", 
        stock: 15,
    },
    {
        name: "Naranja",
        price: "$2.00",
        description: "una naranja", 
        stock: 35,
    },
]

const objectoFrutas = {
        name: "manzana",
        price: "$2.00",
        description: "una manzana", 
    }
</script>



<template>
    <h1>Ejercicio</h1>

    <ul>
        <li v-for="(frutas,index) in arrayFrutas" :key="index" >
            <li v-for="(info,propiedad,index2) in frutas" :key="index2">
                    --> {{ propiedad }}: {{info }}
                </li>   
        </li>

        <li v-for="(frutas,index) in arrayFrutas" :key="index" >
                {{ frutas.name }} - {{ frutas.price }} - {{ frutas.description }}
        </li>

        <br/>
        <p>Elemento de objectoss</p>
        <br/>
        
        <li
            v-for="(value,propiedad) in objectoFrutas" :key="value"
        >
        {{ propiedad }}: {{ value }}

        </li>

        <p>SOLO MAYORES a 10</p>
        <li v-for="(frutas,index) in arrayFrutas" :key="index" >
            <p v-if="frutas.stock >=10">
                <li v-for="(fruta,propiedad) in frutas" :key="index">
                    {{ propiedad }}: {{ fruta }}
                </li>
            </p>  
        </li>
 
        <p>SOLO MAYORES a 10</p>
<br/>
        <template v-for="item in arrayFrutas" :key="item.name">
            <li v-if="item.stock > 0" 
            >{{ item.name }} -> {{ item.price }}</li>
        </template>

    </ul>   
</template>

<style>
h1{
    color: red;
}

</style>