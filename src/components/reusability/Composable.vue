<script setup>
import { useMouse } from './mouse.js'
import { useFetch } from './fetch.js'
const { x, y } = useMouse()

const { data, error } = useFetch('https://dog.ceo/api/breeds/image/random')
</script>

<template>
  <div>
    <h2>コンポーザブル</h2>
    <p>マウスの位置: {{ x }}, {{ y }}</p>

    <div v-if="error">
      <p>エラーが発生しました: {{ error.message }}</p>
    </div>
    <div v-else-if="data">
      <h3>ランダムな犬の画像:</h3>
      <img :src="data.message" alt="Dog" width="200" />
    </div>
  </div>
</template>
