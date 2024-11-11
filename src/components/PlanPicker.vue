<script setup>
import planItem from './PlanPickerItem.vue';
import { ref } from 'vue';
const plans = ref(['El cafetero', 'El chelero', 'El intelectual']);
const selectPlan = (name) => {
  console.log(name);
}
</script>

<template>
    <div class="plans">
      <planItem
      v-for="plan in plans"
      :key="plan"
      :name="plan"
      @select="selectPlan" />
    </div>
</template>

<style scoped>

</style>