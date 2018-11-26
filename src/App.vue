<template>
  <div id="app">
    <select-component/>
    <Select2Component/>
  </div>
</template>

<script>
import SelectComponent from './components/select.vue'
import Select2Component from './components/select.vue'


export default {
  components: {
    SelectComponent,
    Select2Component
  },
 el: '#app',
 data: {
   selected: 2,
   options: [
     { id: 1, text: 'Hello' },
     { id: 2, text: 'World' }
   ]
 }
}
</script>

<style>
#app {
  html, body {
    font: 13px/18px sans-serif;
  }
  select {
    min-width: 300px;
  }
}
</style>
