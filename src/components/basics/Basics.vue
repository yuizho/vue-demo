<script setup>
import Template from './Template.vue'
import Reactivity from './Reactivity.vue'
import Computed from './Computed.vue'
import ClassStyleBinding from './ClassStyleBinding.vue'
import RenderingWithCondition from './RenderingWithCondition.vue'
import ListRendering from './ListRendering.vue'
import EventHandling from './EventHandling.vue'
import FormBinding from './FormBinding.vue'
import Watcher from './Watcher.vue'
import TemplateReference from './TemplateReference.vue'
import Component from './Component.vue'

import { ref } from 'vue'
const componentFontSize = ref(1)
</script>

<template>
  <h1>基本</h1>
  <Template />
  <Reactivity />
  <Computed />
  <ClassStyleBinding />
  <RenderingWithCondition />
  <ListRendering />
  <EventHandling />
  <FormBinding />
  <Watcher />
  <TemplateReference />
  <div :style="{ fontSize: componentFontSize + 'em' }">
    <Component
      title="Hello Vue!"
      @enlarge-text="componentFontSize += 0.1"
      @shrink-text="componentFontSize -= 0.1"
    >
      <p>これは親から渡したテキストです。</p>
    </Component>
  </div>
</template>

<style scoped>
main {
  padding: 1rem;
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
