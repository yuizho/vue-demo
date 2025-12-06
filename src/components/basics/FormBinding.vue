<script setup>
import { ref } from 'vue'

const text = ref('')
const checkedNames = ref([])
const toggle = ref('off')
const age = ref(0)
</script>

<template>
  <div>
    <h2>フォーム入力バインディング</h2>

    <p>Your input: {{ text }}</p>
    <input v-model="text" placeholder="Type something here" />

    <div>
      <p>Checked names: {{ checkedNames.join(', ') }}</p>
      <label><input type="checkbox" value="Alice" v-model="checkedNames" /> Alice</label>
      <label><input type="checkbox" value="Bob" v-model="checkedNames" /> Bob</label>
      <label><input type="checkbox" value="Charlie" v-model="checkedNames" /> Charlie</label>
    </div>

    <div>
      <p>Toggle is {{ toggle }}</p>
      <label>
        <input type="checkbox" v-model="toggle" true-value="on" false-value="off" />
        Toggle
      </label>
    </div>

    <div>
      <p>Age (number type): {{ typeof age }}: {{ age }}</p>
      <input v-model.number="age" />
    </div>
  </div>
</template>

<style scoped></style>
