<script setup>
import { ref } from 'vue'
import Props from './Props.vue'
import Event from './Event.vue'
import VModel from './VModel.vue'
import FololwThrough from './FololwThrough.vue'
import Slot from './Slot.vue'

const title = 'コンポーネントのタイトル'
const callback = (where) => {
  alert(`${where}でイベントが発火しました`)
}
const countModel = ref(0)
</script>

<template>
  <div>
    <h1>コンポーネントの詳細</h1>
    <Props :title="title" />
    <Event @some-event="callback" />
    <VModel v-model="countModel" v-model:title="title" />
    <FololwThrough style="color: red" />
    <Slot> <template v-slot:icon>🐶</template> 親から渡したボタンテキスト </Slot>
  </div>
</template>
