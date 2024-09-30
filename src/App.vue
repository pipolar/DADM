<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import {ref} from 'vue';
const header = ref('App lista  de compras')
const items = ref([
  { id: '0', label: 'bolillos' },
  { id: '1', label: 'pepinillo' },
  { id: '2', label: 'nutella' }
]);
const newItem = ref('');
const newItemHighPriority = ref(false);
const iceCreamFlavors = ref([]);
</script>

<template>
  <h1>
    <i class="material-icons shopping-cart-icon">local_mall</i>
    {{ header }}
  </h1>
  <h1>
    <input type="text" placeholder="Add Item" v-model.trim="newItem">
    <!-- Radio Buttons -->
     <!-- (label>input:radio[v-model="newItemPrioriy"]{$})*2 -->
     <label>
    <input type="checkbox" v-model="newItemHighPriority">
    High Priority
    </label>
    <!-- Helados -->
    <label>
      <input type="checkbox" v-model="iceCreamFlavors" value="vanilla">
      Vanilla
    </label>
    <label>
      <input type="checkbox" v-model="iceCreamFlavors" value="chocolate">
      Chocolate
    </label>
    <label>
      <input type="checkbox" v-model="iceCreamFlavors" value="strawnerry">
      Strawberry
    </label>
    <p>
      {{iceCreamFlavors}}
    </p>
  </h1>
  <ul>
    <li v-for="item in items" :key="id"> ⭐ {{ item.label }} </li>
  </ul>
</template>

<style scoped>
.shopping-cart-icon{
  font-size: 2rem;
}
</style>
