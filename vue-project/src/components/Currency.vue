<script setup>
import { inject } from 'vue';
const currency = inject('currency')
</script>

<template>
   <span>{{ currency }}</span>
</template>