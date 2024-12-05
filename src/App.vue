<script setup>
import fancyButton from './components/FancyButton.vue';
</script>

<template>
  <div class="content">
    <fancyButton>
      <template #icon="slotProps">
        {{ slotProps.hover ? "⭐" : "🌟" }}
      </template>
    </fancyButton>
  </div>
</template>

<style scoped>

</style>