<script setup>
import { defineProps } from 'vue'

defineProps(['title'])
</script>

<template>
  <div>
    <h2>コンポーネントの基礎</h2>
    <p>タイトル: {{ title }}</p>

    <button @click="$emit('enlarge-text')">テキストを大きくする</button>
    <button @click="$emit('shrink-text')">テキストを小さくする</button>

    <slot />
  </div>
</template>
