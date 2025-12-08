<script setup>
import Props from './Props.vue'
const title = 'コンポーネントのタイトル'
</script>

<template>
  <div>
    <h1>コンポーネントの詳細</h1>
    <Props :title="title" />
  </div>
</template>
