<script setup>
import { ref } from 'vue'

const show = ref(false)
</script>

<template>
  <div>
    <h2>トランジション</h2>
    <button @click="show = !show">Toggle</button>
    <Transition name="fade">
      <p v-if="show">hello</p>
    </Transition>

    <Transition name="bounce">
      <p v-if="show" style="text-align: center">Hello here is some bouncy text!</p>
    </Transition>
  </div>
</template>

<style scoped>
/* これらのクラスが何をするかは後ほど説明します! */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}

.bounce-enter-active {
  animation: bounce-in 0.5s;
}
.bounce-leave-active {
  animation: bounce-in 0.5s reverse;
}
@keyframes bounce-in {
  0% {
    transform: scale(0);
  }
  50% {
    transform: scale(2);
  }
  100% {
    transform: scale(1);
  }
}
</style>
