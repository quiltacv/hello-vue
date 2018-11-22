<template>
    <div class="my-component">
        <div> {{ message }} - {{ reverseMessage }}</div>
        <div> Count Click: {{ countClicks }}</div>

        <div><button @click="sayHello">Click me</button></div>
    </div>
</template>
<script>
  export default{
    data() {
      return {
        message: "FoxZi Vue hello",
        countClicks: 0
      }
    },

    computed: {
      reverseMessage() {
        return this.message.split('').reverse().join('')
      },
      countClick(){
        return this.countClicks
      }
    },

    methods: {
      sayHello() {
        this.countClickM()
        return this.message = 'this fun'
      },
      countClickM() {
        return this.countClicks++
      }
    },

    watch: {
      countClick() {
        console.log("changed count")
      },
      message() {
        console.log("changed messages")
      }
    }
  }
</script>
