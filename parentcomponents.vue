<!-- ParentComponent.vue -->
<script setup>
import { ref } from 'vue'
import ChildComponent from './ChildComponent.vue' // pastikan path-nya sesuai

const messageFromChild = ref('')

const handleChildClick = (msg) => {
  messageFromChild.value = msg
}
</script>

<template>
  <div>
    <h1>Parent Component</h1>
    <p>Pesan dari child: {{ messageFromChild }}</p>

    <!-- Gunakan ChildComponent -->
    <ChildComponent 
      message="Halo dari Parent!"
      @child-clicked="handleChildClick"
    >
      <p>Ini dikirim dari parent ke slot child!</p>
    </ChildComponent>
  </div>
</template>
