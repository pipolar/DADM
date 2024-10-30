<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import {ref} from 'vue';
const header = ref('App lista  de compras')
// items
// Item-Model
const items = ref([
  { id: '0', label: 'bolillos', purchased: false, priority: true},
  { id: '1', label: 'pepinillo', purchased: true, priority: true},
  { id: '2', label: 'nutella', purchased: false, priority: false}
]);
// Item Method
const saveItem = () => {
  items.value.push({ id: items.value.length + 1, label: newItem.value });
  // Clean the input
  newItem.value = '';
}

const activateEdition = (activate) => {
  editing.value = activate;
}

const validation = () => {
  if (newItem.value == "") {
  }
}


// Formulario
const newItem = ref('');
const newItemHighPriority = ref(false);
const editing = ref(true);
const link = ref('https://www.google.com')

// Eventos


</script>

<template>
  <div class="header">
    <h1>
      <i class="material-icons shopping-cart-icon">local_mall</i>
      {{ header }}
    </h1>
    <button v-if="editing" class="btn" @click="activateEdition(false)">Cancelar</button>
    <button v-else class="btn btn-primary" @click="activateEdition(true)">Agregar Articulo</button>
  </div>
    <!-- Agrupando en un div las entradas -->
  <form
  class="add-item form"
  v-if="editing"
  v-on:submit.prevent="saveItem">
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
      :disabled="newItem.length === 0"
      class="btn btn-primary"
    >
      Save Item
    </button>
  </form>
  <!-- Lista clase con objetos -->
  <ul>
    <li 
      v-for="{label, id, purchased, priority} in items"
      :key="id"
      class="amazing"
      :class="{ strikeout: purchased, priority: priority}"> {{ priority ? "🔥" : "🛍️" }} {{ label }} </li>
  </ul>
  <!-- Lista clase con arreglos -->
  <ul>
    <li
      v-for="{ id, label, purchased, priority } in items"
      v-bind:key="id"
      :class="{ strikeout: purchased, priority}"
    >
      ⚜ {{ label }}
    </li>
  </ul>
  <p v-if="items.length === 0">🥀 NO HAY ELEMENTOS EN LA LISTA 🥀</p>
</template>

<style scoped>
.shopping-cart-icon{
  font-size: 2rem;
}
</style>
