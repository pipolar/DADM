<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'
import {ref} from 'vue';
const header = ref('App lista  de compras')
// items
// Item-Model
const items = ref([
  { id: '0', label: 'bolillos' },
  { id: '1', label: 'pepinillo' },
  { id: '2', label: 'nutella' }
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

// Formulario
const newItem = ref('');
const newItemHighPriority = ref(false);
const editing = ref(true);

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
  <!-- Colocando un hyperlink -->
   <a v-bind:href="'https://' + newItem" v-if="newItem = www.google.com" target="_blank">{{ newItem == "" ? "🔥 Link" : newItem }}</a>
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
      class="btn btn-primary"
    >
      Save Item
    </button>
  </form>
  <ul>
    <li v-for="item in items" :key="id"> ⭐ {{ item.label }} </li>
  </ul>
  <p v-if="items.length === 0">🥀 NO HAY ELEMENTOS EN LA LISTA 🥀</p>
</template>

<style scoped>
.shopping-cart-icon{
  font-size: 2rem;
}
</style>
