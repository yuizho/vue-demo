<script setup>
// events can define explicitly
defineEmits(['someEvent'])
</script>

<template>
  <div>
    <h2>イベント</h2>
    <button @click="$emit('someEvent', '子供')">イベントを発火</button>
  </div>
</template>
