<script setup>
import { ref } from 'vue'
import Template from './components/basics/Template.vue'
import Reactivity from './components/basics/Reactivity.vue'
import Computed from './components/basics/Computed.vue'
import ClassStyleBinding from './components/basics/ClassStyleBinding.vue'
import RenderingWithCondition from './components/basics/RenderingWithCondition.vue'
import ListRendering from './components/basics/ListRendering.vue'
import EventHandling from './components/basics/EventHandling.vue'
import FormBinding from './components/basics/FormBinding.vue'
import Watcher from './components/basics/Watcher.vue'
import TemplateReference from './components/basics/TemplateReference.vue'
import Component from './components/basics/Component.vue'

const plainMsg = 'Welcome to Your Vue.js App'
const dynamicId = 'welcome-message'
const rawHtml = '<h2>This is h2 rendered from raw HTML.</h2>'
const isDisabled = true
const objectOfAttrs = {
  id: 'multi-attrs-message',
  class: 'multi-attrs',
  style: 'color: blue; font-weight: bold;',
}
const seen = true
const showAlert = (eventName) => {
  alert(`${eventName} event triggered!`)
}
const attributeName = 'href'
const url = 'https://vuejs.org/'
const eventName = 'mouseover'

const componentFontSize = ref(1)
</script>

<template>
  <main>
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
  </main>
</template>

<style scoped>
main {
  padding: 1rem;
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
</style>
