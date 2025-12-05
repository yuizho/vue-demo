<script setup>
import { ref, reactive } from 'vue'

const items = ref([{ message: 'Foo' }, { message: 'Bar' }])
const myObject = reactive({
  title: 'Hello Vue 3',
  description: 'This is a simple example of Vue 3 composition API.',
  publishedAt: '2024-06-01',
})

const todos = ref([
  { id: 1, text: 'Learn JavaScript', done: true },
  { id: 2, text: 'Learn Vue', done: false },
  { id: 3, text: 'Build something awesome', done: false },
])
</script>

<template>
  <div>
    <h2>リストレンダリング</h2>
    <h3>List</h3>
    <ul>
      <li v-for="(item, index) in items">{{ index }} - {{ item.message }}</li>
    </ul>

    <h3>Object</h3>
    <ul>
      <li v-for="(value, key, index) in myObject">{{ index }} - {{ key }} : {{ value }}</li>
    </ul>

    <h3>range</h3>
    <ul>
      <li v-for="n in 3">{{ n }}</li>
    </ul>

    <h3>filtering</h3>
    <ul>
      <!-- keyを指定することで既存のDOM要素の再利用が可能になる -->
      <template v-for="todo in todos" :key="todo.id">
        <li v-if="!todo.done">{{ todo.text }}</li>
      </template>
    </ul>
  </div>
</template>

<style scoped></style>
