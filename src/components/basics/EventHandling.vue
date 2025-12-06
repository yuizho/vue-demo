<script setup>
import { ref } from 'vue'

const count = ref(0)
const name = ref('Vue.js')

function greet(event) {
  alert(`Hello, ${name.value}!`)
  if (event) {
    alert(event.target.tagName)
  }
}

function warn(message, event) {
  if (event) {
    event.preventDefault()
  }
  alert(message)
}
</script>

<template>
  <div>
    <h2>イベントハンドリング</h2>

    <button @click="count++">Add 1</button>
    <p>Count: {{ count }}</p>

    <button @click="greet">Greet</button>

    <br />
    <button @click="(event) => warn('Form cannot be submitted yet.', event)">Submit</button>

    <br />
    <a @click.prevent="greet" href="https://vuejs.org/"
      >prevent default a behavior by event modifier</a
    >

    <input @keyup.alt.enter="greet" placeholder="Press Alt + Enter to Greet to show alert dialog" />
  </div>
</template>

<style scoped></style>
