<script setup>
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
  <h2>テンプレート構文</h2>
  <p :id="dynamicId">Message: {{ plainMsg }}</p>
  <p v-html="rawHtml"></p>
  <button :disabled="isDisabled">Click me</button>
  <p v-bind="objectOfAttrs">multiple attrs are configured by v-bind</p>
  <p v-if="seen">Now you see me</p>
  <p v-else>Now you don't</p>
  <button @click="showAlert('click')">Show Alert</button>
  <br />
  <a :[attributeName]="url">Vue Official Website</a>
  <br />
  <button v-on:[eventName]="showAlert(eventName)">Show Alert via v-on:mouseover</button>
  <br />
  <input @keyup.enter="showAlert('enter key')" placeholder="Press Enter" />
</template>
