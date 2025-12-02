<script setup>
import { ref, reactive } from 'vue'
const count = ref(0)
// 基本はrefを使ったほうがよい
// https://ja.vuejs.org/guide/essentials/reactivity-fundamentals.html#limitations-of-reactive
const state = reactive({ count: 0 })
</script>

<template>
  <div>
    <h2>リアクティビティ</h2>
    <button @click="count++">{{ count }} by ref</button>
    <br />
    <button @click="state.count++">{{ state.count }} by reactive</button>
  </div>
</template>
