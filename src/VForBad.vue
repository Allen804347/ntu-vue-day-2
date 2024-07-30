<script setup>
import { ref } from "vue";

const items = ref([
  { id: 1, text: 'Item 1' },
  { id: 2, text: 'Item 2' },
  { id: 3, text: 'Item 3' }
]);

const changeItems = () => {
  items.value = [
    { id: 1, text: 'New Item 1' },
    { id: 2, text: 'New Item 2' },
    { id: 3, text: 'New Item 3' }
  ];
};

</script>

<template>
  <div id="app">
    <ul>
      <li v-for="item in items" :key="item.id">{{ item.text }}</li>
    </ul>
    <button @click="changeItems">Change Items</button>
  </div>
</template>