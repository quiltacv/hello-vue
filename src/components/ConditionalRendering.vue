<template>
    <div class="conditional-rendering">
        <div class="block-1" v-if="isActive == false">
            This is block 1
        </div>
        <div class="block-2" v-else>
            This is block 2
        </div>
        <div>
          <button @click="toggleActive">Button</button>
        </div>
    </div>
</template>

<script>
  export default{
    data() {
      return {
        isActive: true
      }
    },
    methods: {
      toggleActive() {
        return this.isActive = !this.isActive
      }
    }
  }
</script>
