<script setup>
import planItem from './PlanPickerItem.vue';
import { ref } from 'vue';
// Creando una referencia reactiva
// para almacenar el plan seleccionado
const selectedPlan = ref(null);
const plans = ref(['El cafetero', 'El chelero', 'El intelectual']);
const selectPlan = (name) => {
  // Almacenar el plan seleccionado
  selectedPlan.value = name;
}
</script>

<template>
    <div class="plans">
      <planItem
      v-for="plan in plans"
      :key="plan"
      :name="plan"
      @select="selectPlan"
      :select-plan="selectPlan" />
    </div>
    <p>{{ selectedPlan }}</p>
</template>

<style scoped>

</style>