
<script setup>
import {onMounted, ref} from 'vue'
import {defineProps} from 'vue'
const leo ="public/Leopard1.jpeg"

const props = defineProps({
    item:Object
})

console.log(props.item)
</script>
<template>
<div class = "tank_card">
    <h3>{{ props.item.name }}</h3>
    <p class = "image-container">
        <img :src = leo>
    </p>
    <grid class = "grid-container">
        <p>Nation: {{ props.item.nation }}</p>
        <p>Caliber: {{ props.item.caliber }}</p>
        <p>Speed: {{ props.item.speed }}</p>
        <p>Dispersion: {{ props.item.dispersion }}</p>
    </grid>
    <div class = "flex-row">
        <button class = "drop-shadow">Edit</button>
        <button class = "drop-shadow red">delete</button>
    </div>
    
</div>


</template>