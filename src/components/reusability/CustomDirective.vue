<script setup>
// カスタムディレクティブはDOMを直接操作しないと行けないときだけに使うこと！！
// https://ja.vuejs.org/guide/reusability/custom-directives.html#when-to-use

// 接頭辞が v で始まるキャメルケースの変数をカスタムディレクティブとして使用することができる
const vHighligt = {
  mounted: (el) => {
    el.classList.add('is-highlight')
  },
}
</script>

<template>
  <div>
    <h2>カスタムディレクティブ</h2>
    <p v-highligt>このテキストはハイライトされています。</p>
  </div>
</template>

<style scoped>
.is-highlight {
  background-color: orange;
}
</style>
