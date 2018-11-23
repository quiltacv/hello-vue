<template>
  <ul id="app">
    <tree class="item" :model="treeData"></tree>
  </ul>
</template>

<script>
import Tree from './components/Tree.vue'

var data = {
  name: 'My Tree',
  children: [
    { name: 'hello' },
    { name: 'wat' },
    {
      name: 'child folder',
      children: [
        {
          name: 'child folder',
          children: [
            { name: 'hello' },
            { name: 'wat',
              children: [
                {name: 'child folder'}
              ]
            }
          ]
        },
        { name: 'hello' },
        { name: 'wat' },
        {
          name: 'child folder',
          children: [
            { name: 'hello' },
            { name: 'wat' }
          ]
        }
      ]
    }
  ]
}
export default {
  name: 'app',
  components: {
    Tree
  },
  data() {
    return {
      treeData: data
    }
  }
}
</script>
