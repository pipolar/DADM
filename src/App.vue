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
    <!-- Agrupando en un div las entradas -->
  <form v-on:submit.prevent="items.push({ id: items.length + 1, label: newItem })" class="add-item fomr">
    <!-- entrada de texto -->
    <input
      v-model.trim="newItem"
      type="text"
      placeholder="Add Item"
    />
    <!-- Caja de seleccion de prioridad -->
    <label>
      <input type="checkbox" v-model="newItemHighPriority" />
      High Priority
    </label>
    <!-- Boton -->
    <button
      class="btn btn-primary"
    >
      Save Item
    </button>
  </form>
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
