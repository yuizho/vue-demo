<script setup>
const model = defineModel()
const title = defineModel('title', { required: true })

function update() {
  model.value++
}
</script>

<template>
  <div>
    <h2>v-model</h2>
    <div>Parent bound v-model is: {{ model }}</div>
    <button @click="update">Increment from Child</button>
    <br />
    <input v-model="title" />
  </div>
</template>
