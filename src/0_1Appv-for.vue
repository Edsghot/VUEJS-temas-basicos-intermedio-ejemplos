<script setup>
const name = "Erick"
const arrayFrutas = ["🍓","🍇","🍑","🍊","🍍"]
</script>

<template>
  <h1>Hola {{ name.toUpperCase() }}</h1>
  <br/>
  <ul>
    <li 
      v-for="(fruta,index) in arrayFrutas" 
      :key="index"
    >{{ index }} -> {{ fruta }}</li>
  </ul>

</template>

<style>
h1{
  color: brown;
}
</style>