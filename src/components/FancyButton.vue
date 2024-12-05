<template>
    <button>
        <slot name="icon">➡️</slot>
        <slot>Submit</slot>
    </button>
</template>
  
<script setup>
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