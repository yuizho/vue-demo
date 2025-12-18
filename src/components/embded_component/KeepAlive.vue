<script setup>
import { shallowRef } from 'vue'
import CompA from './CompA.vue'
import CompB from './CompB.vue'
// 切り替えるコンポーネントを管理
// ※コンポーネントそのものを入れる場合は shallowRef が推奨されます（無駄なリアクティブ化を防ぐため）
const currentComp = shallowRef(CompA)
</script>

<template>
  <div>
    <h2>KeepAlive</h2>

    <div>
      <button @click="currentComp = CompA">Tag A(Counter)</button>
      <button @click="currentComp = CompB">Tag B(Input)</button>
    </div>

    <!-- KeepAliveで囲むことで、コンポーネントの状態を保持できる -->
    <KeepAlive>
      <component :is="currentComp" />
    </KeepAlive>
  </div>
</template>

<style scoped></style>
