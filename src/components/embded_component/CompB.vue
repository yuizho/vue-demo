<script setup>
import { ref } from 'vue'
const text = ref('')
</script>

<template>
  <div class="box">
    <h3>Component B</h3>
    <input v-model="text" placeholder="文字を入力してタブを切り替えてみて" />
  </div>
</template>
