<script setup>
import { ref } from 'vue'

const isActive = ref(true)
const hasError = ref(false)
</script>

<template>
  <div>
    <h2>クラスとスタイルのバインディング</h2>
    <div class="static" :class="{ active: isActive, 'text-danger': hasError }">hoge</div>
  </div>
</template>

<style scoped>
.active::after {
  content: ' (active)';
  color: green;
}

.text-danger {
  color: red;
}
</style>
