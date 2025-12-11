<script setup>
import Props from './Props.vue'
import Event from './Event.vue'
const title = 'コンポーネントのタイトル'
const callback = (where) => {
  alert(`${where}でイベントが発火しました`)
}
</script>

<template>
  <div>
    <h1>コンポーネントの詳細</h1>
    <Props :title="title" />
    <Event @some-event="callback" />
  </div>
</template>
