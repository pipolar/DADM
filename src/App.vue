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
     <label><input type="checkbox" v-model="newItemHighPriority">Alta Prioridad</label>
     <p>
      {{ newItemHighPriority }}
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
