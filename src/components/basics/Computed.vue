<script setup>
import { reactive, computed } from 'vue'
const author = reactive({
  name: 'John Doe',
  books: ['Vue 2 - Advanced Guide', 'Vue 3 - Basic Guide', 'Vue 4 - The Mystery'],
})

const publishedBooksMessage = computed(() => {
  return author.books.length > 0 ? 'Has books' : 'No books'
})
</script>

<template>
  <div>
    <h2>算出プロパティ</h2>
    <span>{{ publishedBooksMessage }}</span>
  </div>
</template>
