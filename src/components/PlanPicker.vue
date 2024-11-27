<script setup>
import PlanPickerItem from './PlanPickerItem.vue';
import { onUnmounted, onMounted, ref } from 'vue';
// Creando una referencia reactiva
// para almacenar el plan seleccionado
const selectedPlan = ref(null);
const plans = ref(['El cafetero', 'El chelero', 'El intelectual']);
const selectPlan = (name) => {
  // Almacenar el plan seleccionado
  selectedPlan.value = name;
};

const plansWrapper = ref(null);

//intentando obtener la referencia al elemento .plans
 
console.log("termina de ejecutar el script setup 🧸");
 
//registrando el hook mounted
onMounted(() => {
  console.log("el componente planPiker de ha montado 🎉")
  console.log(plansWrapper.value);
});

// registrando el hook unmounted
onUnmounted(() => {
  console.log("El componente PlanPicker se ha desmontado")
});
</script>

<template>
    <div red="plansWrapper" class="plans">
      <PlanPickerItem
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