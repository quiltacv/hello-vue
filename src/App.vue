<template>
  <ul id="app">
    <item>
      <Tree :model="treeData"></Tree>
    </item>
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
            { name: 'wat' }
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
