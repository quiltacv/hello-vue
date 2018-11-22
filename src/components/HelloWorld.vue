<template>
    <div class="my-component">
        <div>{{ message.split('').reverse().join('') }}</div>
        <div><button @click="sayHello">Click me</button></div>
    </div>
</template>
<script>
  export default{
    data() {
      return {
        message: "FoxZi Vue hello"
      }
    },
    methods: {
      sayHello() {
        return this.message = 'this fun'
      }
    }
  }
</script>
