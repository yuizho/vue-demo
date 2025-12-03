<script setup>
import { reactive, computed, ref } from 'vue'
const author = reactive({
  name: 'John Doe',
  books: ['Vue 2 - Advanced Guide', 'Vue 3 - Basic Guide', 'Vue 4 - The Mystery'],
})
const publishedBooksMessage = computed(() => {
  return author.books.length > 0 ? 'Has books' : 'No books'
})

// 書き込み可能な算出プロパティ
const firstName = reactive({ value: 'John' })
const lastName = reactive({ value: 'Doe' })
const fullName = computed({
  get() {
    return `${firstName.value} ${lastName.value}`
  },
  set(newValue) {
    const names = newValue.split(' ')
    firstName.value = names[0] || ''
    lastName.value = names[1] || ''
  },
})

// 前回の値を取得する
const count = ref(2)
const alwaysSmall = computed({
  get(previous) {
    if (count.value <= 3) {
      return count.value
    }

    return previous
  },
  set(newValue) {
    count.value = newValue
  },
})
</script>

<template>
  <div>
    <h2>算出プロパティ</h2>
    <span>{{ publishedBooksMessage }}</span>

    <h3>書き込み可能な算出プロパティ</h3>
    <p>First Name: {{ firstName.value }}</p>
    <p>Last Name: {{ lastName.value }}</p>
    <p>Full Name: {{ fullName }}</p>
    <input v-model="fullName" placeholder="Enter full name" />

    <h3>前回の値を取得する算出プロパティ</h3>
    <p>count: {{ count }}</p>
    <p>alwaysSmall: {{ alwaysSmall }}</p>
    <button @click="alwaysSmall++">Increment Count</button>
    <button @click="alwaysSmall--">decrement Count</button>
  </div>
</template>
