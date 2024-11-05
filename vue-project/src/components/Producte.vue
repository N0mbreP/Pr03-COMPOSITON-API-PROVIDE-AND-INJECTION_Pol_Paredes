<script setup>
import { inject } from 'vue';
const currency = inject('currency')
const props = defineProps({
    productName:String,
    productPrice:String
})
const emit= defineEmits(['enviarProducte'])
const enviarProducte=()=>{
    emit('enviarProducte', props.productName)
}
</script>

<template>
    <li>{{ productName }} - {{ productPrice }} {{ currency }}  <button @click="enviarProducte">Add to order</button></li>
</template>