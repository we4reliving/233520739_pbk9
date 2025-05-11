<script setup>
import { defineProps, defineEmits } from 'vue'

const props = defineProps({
  message: String
})

const emit = defineEmits(['child-clicked'])

const handleClick = () => {
  emit('child-clicked', 'Halo dari Child!')
}
</script>

<template>
  <div class="card">
    <h2>MASUK KE MENU</h2>
    <p>{{ message }}</p>
    
    <slot></slot>

    <button @click="handleClick">Klik untuk pilih menu</button>
  </div>
</template>

<style scoped>
.card {
  border: 2px solid #42b983;
  border-radius: 10px;
  padding: 1.5rem;
  background-color: white;
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
  text-align: center;
  max-width: 300px;
  margin: auto;
}
button {
  margin-top: 1rem;
  background-color: #42b983;
  color: white;
  border: none;
  padding: 0.6rem 1rem;
  border-radius: 6px;
  font-weight: bold;
  cursor: pointer;
  transition: background-color 0.3s;
}
button:hover {
  background-color: #369f72;
}
</style>
