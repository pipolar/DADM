<template>
    <button
    @mouseenter="hover = true"
    @mouseleave="hover = false">
        <slot name="icon">➡️</slot>
        <slot>Submit</slot>
    </button>
    {{ hover }}
</template>
  
<script setup>
import { ref } from 'vue';
const hover = ref(false)
</script>
  
<style scoped>
html {
font-family: sans-serif;
}

.content{
  text-align: center;
}

button{
  width: 12rem;
  margin: 30px auto;
  font-size: 2rem;
}
</style>