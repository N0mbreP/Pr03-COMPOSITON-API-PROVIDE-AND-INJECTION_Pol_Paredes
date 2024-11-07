<script setup>
import Currency from './Currency.vue';
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
    <li>{{ productName }} - {{ productPrice }} <Currency/>  <button @click="enviarProducte">Add to order</button></li>
</template>