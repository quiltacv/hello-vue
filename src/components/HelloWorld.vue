<template>
    <div class="my-component">
        <div>{{ message }}</div>
        <div><button @click="sayHello">Click me</button></div>
    </div>
</template>
<script>
  export default{
    data() {
      return {
        message: "adadadad"
      }
    },
    methods: {
      sayHello() {
        return this.message = 'this fun'
      }
    }
  }
</script>
