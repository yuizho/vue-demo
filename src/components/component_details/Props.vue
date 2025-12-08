<script setup>
const props = defineProps({
  title: {
    type: String,
    required: true,
  },
  likes: {
    type: Number,
    default: -1,
  },
})
</script>

<template>
  <div>
    <h2>登録</h2>
    <p>タイトル: {{ title }}</p>
    <p>いいね数: {{ likes }}</p>
  </div>
</template>
