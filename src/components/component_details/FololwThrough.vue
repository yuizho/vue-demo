<script setup>
import { useAttrs } from 'vue'

// 以下を有効にすると親から渡された属性を継承しなくなる)
// defineOptions({ inheritAttrs: false })

const attrs = useAttrs()
console.table(attrs)
</script>

<template>
  <h2>フォロースルー属性</h2>
  <p v-bind="$attrs">親から渡された属性ここに継承する</p>
</template>
