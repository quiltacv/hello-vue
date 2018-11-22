<template>
    <div class="my-component">
        <div> {{ message }} - {{ reverseMessage }}</div>
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
    computed: {
      reverseMessage() {
        return this.message.split('').reverse().join('')
      }
    },
    methods: {
      sayHello() {
        return this.message = 'this fun'
      }
    }
  }
</script>
