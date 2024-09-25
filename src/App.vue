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
const newItemPriority = ref('low');
</script>

<template>
  <h1>
    <i class="material-icons shopping-cart-icon">local_mall</i>
    {{ header }}
  </h1>
  <h1>
    <input v-model="newItem" type="text" placeholder="Agregar articulo">
    <!-- Radio Buttons -->
     <!-- (label>input:radio[v-model="newItemPrioriy"]{$})*2 -->
    <label><input type="radio" value="low" v-model="newItemPriority">
      Baja
    </label>
    <label><input type="radio" value="high" v-model="newItemPriority">
      Alta
    </label>
    {{ newItemPriority == 'low' ? '🧊' : '🔥' }}
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
