<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <ConditionalRendering/>
    <ListRendering/>

    <ListRendering v-for="n in 10" :key="n"></ListRendering>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ConditionalRendering from './components/ConditionalRendering.vue'
import ListRendering from './components/ListRendering.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    ConditionalRendering,
    ListRendering
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
