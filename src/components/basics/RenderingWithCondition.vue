<script setup>
import { ref } from 'vue'

const awesome = ref(true)
const showHello = ref(true)
</script>

<template>
  <div>
    <h2>条件付きレンダリング</h2>

    <div>
      <button @click="() => (awesome = !awesome)">Toggle</button>
      <p v-if="awesome">Vue is awesome!!!!</p>
      <p v-else>Oh no...</p>
    </div>

    <p v-show="showHello">v-show hide the node by display: none;</p>
  </div>
</template>

<style scoped></style>
