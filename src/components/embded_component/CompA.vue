<script setup>
import { ref, onMounted, onUnmounted, onActivated, onDeactivated } from 'vue'

const count = ref(0)

// --- 通常のライフサイクル ---
onMounted(() => {
  // 初回表示の1回だけ実行される
  console.log('CompA: Mounted (初期化)')
})

onUnmounted(() => {
  // KeepAlive内だと、基本的には呼ばれない！（親が消えるまで生き続ける）
  console.log('CompA: Unmounted (破棄)')
})

// --- KeepAlive専用のライフサイクル ---
onActivated(() => {
  // タブが表示されるたびに実行される
  // 例: 最新データの再取得などを行うならここ
  console.log('CompA: Activated (表示・復帰)')
})

onDeactivated(() => {
  // タブが隠れるたびに実行される
  // 例: アニメーションの一時停止など
  console.log('CompA: Deactivated (非表示・待機)')
})
</script>

<template>
  <div class="box">
    <h3>Component A</h3>
    <p>Count: {{ count }}</p>
    <button @click="count++">Increment</button>
  </div>
</template>
