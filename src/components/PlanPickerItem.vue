<template>
    <div @click="selectPlan" class="plan">
      <div class="description">
        <span class="title">
          {{ name }} {{ isSelected ? '🛑' : '' }}
        </span>
      </div>
    </div>
  </template>
  
  <script setup>
  // Importando la funcion para crear
  // propiedad computada
  import { computed } from 'vue';
  // Usando un macro para
  // definir las props
  const props = defineProps({
      name: {
          type: String,
          required: true
      },
      selectPlan: String
  });
  // Define event
  const emit = defineEmits(['select']);

  // Funcion que permite cammbiar el estado de la variable
  // selected
  const selectPlan = () => {
    // Emitir evento de que el
    // plan ha sido seleccionado
    emit('select', props.name)
  }
  // Creando una propiedad computada
  // Pra asaber si el plan ha sido seleccionado
  const isSelected = computed(() => {
    return props.name === props.selectedPlan;
  })
  </script>
  
  <style lang="scss" scoped>
  
  </style>