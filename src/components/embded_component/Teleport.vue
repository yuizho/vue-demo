<script setup>
import { ref } from 'vue'
const open = ref(false)
</script>

<template>
  <div>
    <h2>Teleport</h2>
    <button @click="open = true">Open Modal</button>

    <Teleport defer to="body">
      <div v-if="open" class="modal">
        <p>Hello from the modal!</p>
        <button @click="open = false">Close</button>
      </div>
    </Teleport>
  </div>
</template>

<style scoped>
.modal {
  position: fixed;
  z-index: 999;
  top: 50%;
  left: 50%;
  width: 300px;
  margin-left: -150px;
  border: 1px solid #ccc;
  padding: 20px;
  border-radius: 8px;
  background-color: white;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.2);
}
</style>
