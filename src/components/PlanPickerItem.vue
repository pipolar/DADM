<template>
  <div @click="selectPlan" class="plan">
    <div class="description">
      <span class="title">
        {{ name }} {{ selected ? '🛑' : '' }}
      </span>
    </div>
  </div>
</template>

<script setup>
// importando ref
import { ref } from 'vue';
// Usando un macro para
// definir las props
const props = defineProps({
    name: {
        type: String,
        required: true
    }
});
// Define event
const emit = defineEmits(['select']);
// Variable que permite
// recirdar si el plan ha sido seleccionado
const selected = ref(false);
// Funcion que permite cammbiar el estado de la variable
// selected
const selectPlan = () => {
  selected.value = true;
  // Emitir evento de que el
  // plan ha sido seleccionado
  emit('select', props.name)
}
</script>

<style lang="scss" scoped>

</style>