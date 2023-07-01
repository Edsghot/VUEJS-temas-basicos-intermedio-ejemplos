<script setup>
    const name="Vue dinamico"

    const handleClick=(meesage)=>{
        console.log("me diste click "+meesage)
    }
</script>

<template>
    <h1>Hola </h1>
    <button v-on:click.right.prevent="handleClick('right')">Activame right</button>
    <button @click.left="handleClick('left')">Activame left</button>
    <button @click.middle="handleClick('Middle')">Activame middle</button>
</template>

<style>
</style>