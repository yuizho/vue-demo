<script setup>
import { useAttrs } from 'vue'
</script>

<template>
  <h2>スロット</h2>
  <button class="fancy-btn">
    <slot name="icon">
      <span>⭐</span>
    </slot>
    <slot>デフォルトのボタンテキスト</slot>
  </button>
</template>
