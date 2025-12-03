<script setup>
import HelloWorld from './components/HelloWorld.vue'
import Template from './components/basics/Template.vue'
import Reactivity from './components/basics/Reactivity.vue'
import Computed from './components/basics/Computed.vue'

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
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />

    <div class="wrapper">
      <HelloWorld msg="You did it!!!!!" />
    </div>
  </header>

  <main>
    <h1>基本</h1>
    <Template />
    <Reactivity />
    <Computed />
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
