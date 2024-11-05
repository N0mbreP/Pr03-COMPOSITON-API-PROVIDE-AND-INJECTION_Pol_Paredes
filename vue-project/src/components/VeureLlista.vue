<script setup>

const emit= defineEmits(['enviarProducte'])
const enviarProducte=()=>{
    emit('enviarProducte', productName)
}
</script>

<template>
   <button @click="enviarProducte">Add to order</button>
</template>