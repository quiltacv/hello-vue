<template>
  <div id="app" @touchmove.prevent>
    <Header>
      <template slot="header">
        <h1>Elastic Draggable SVG Header</h1>
        <p>with <a href="http://vuejs.org">Vue.js</a> + <a href="http://dynamicsjs.com">dynamics.js</a></p>
      </template>
      <template slot="content">
        <p>Note this is just an effect demo - there are of course many additional details if you want to use this in production, e.g. handling responsive sizes, reload threshold and content scrolling. Those are out of scope for this quick little hack. However, the idea is that you can hide them as internal details of a Vue.js component and expose a simple Web-Component-like interface.</p>
      </template>
    </Header>
  </div>
</template>

<script>
import Header from './components/header.vue'

export default {
  name: 'app',
  components: {
    Header
  }
}
</script>

<style>
h1 {
  font-weight: 300;
  font-size: 1.8em;
  margin-top: 0;
}
a {
  color: #fff;
}
.draggable-header-view {
  background-color: #fff;
  box-shadow: 0 4px 16px rgba(0,0,0,.15);
  width: 320px;
  height: 560px;
  overflow: hidden;
  margin: 30px auto;
  position: relative;
  font-family: 'Roboto', Helvetica, Arial, sans-serif;
  color: #fff;
  font-size: 14px;
  font-weight: 300;
  -webkit-user-select: none;
  -moz-user-select: none;
  -ms-user-select: none;
  user-select: none;
}
.draggable-header-view .bg {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 0;
}
.draggable-header-view .header, .draggable-header-view .content {
  position: relative;
  z-index: 1;
  padding: 30px;
  box-sizing: border-box;
}
.draggable-header-view .header {
  height: 160px;
}
.draggable-header-view .content {
  color: #333;
  line-height: 1.5em;
}

</style>
