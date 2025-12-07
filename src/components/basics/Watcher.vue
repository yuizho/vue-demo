<script setup>
import { ref, reactive, watch } from 'vue'
const count = ref(0)

const x = ref(0)
const y = ref(0)

watch(
  () => x.value + y.value,
  (sum) => console.log(`x + y = ${sum}`),
)

const obj = reactive({ count: 0 })
watch(
  obj,
  (newValue, oldValue) => {
    console.log(`obj changed: ${JSON.stringify(newValue)}`)
  },
  { deep: true },
)
</script>

<template>
  <div>
    <h2>ウォッチャー</h2>

    <div>
      <h3>基本的なウォッチャー</h3>
      <p>x: {{ x }}, y: {{ y }}</p>
      <button @click="x++">x++</button>
      <button @click="y++">y++</button>
    </div>

    <div>
      <h3>ディープウォッチャー</h3>
      <p>count: {{ obj.count }}</p>
      <button @click="obj.count++">obj.count++</button>
    </div>
  </div>
</template>
