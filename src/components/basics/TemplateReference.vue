<script setup>
import { useTemplateRef, onMounted } from 'vue'

const input = useTemplateRef('my-input')
onMounted(() => {
  input.value.focus()
})
</script>

<template>
  <div>
    <h2>テンプレート参照</h2>
    <input ref="my-input" />
  </div>
</template>
