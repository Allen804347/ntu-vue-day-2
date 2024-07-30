<script setup>
import { ref } from 'vue'

const data = ref([
  { id: 1, name: 'Bubble Tea', price: 4, description: 'A sweet and refreshing tea with tapioca pearls.' },
  { id: 2, name: 'Milkshake', price: 5, description: 'A creamy and delicious milkshake with various flavors.' },
  { id: 3, name: 'Smoothie', price: 6, description: 'A healthy and fruity smoothie with fresh ingredients.' }
])

const currentId = ref(null)

const close = () => {
  currentId.value = null
}
const open = (targetId) => {
  currentId.value = targetId
}
</script>

<template>
  <p>Drink Menu</p>
  <ul>
    <li v-for="item in data" :key="item.id" @click="open(item.id)">
      <p>{{ item.name }} - ${{item.price}}</p>
      <div v-if="currentId === item.id">
        <p>{{ item.description }}</p>
        <button @click.stop="close">close</button>
      </div>
    </li>
  </ul>
</template>
