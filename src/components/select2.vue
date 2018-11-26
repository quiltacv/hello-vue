<template>
  <select>
    <slot></slot>
  </select>
</template>
<script>
  export default{
    props: ['options', 'value']
    mounted() {
      var vm = this
      $(this.$app)
        .select2({data: this.options})
        .val(this.value)
        .trigger('change')
        .on('change', function(){
          vm.$emit('input', this.value)
        })
    },
    watch: {
      value(value){
        $(this.$app).val(value).trigger('change')
      },
      options(options) {
        $(this.$app).empty().select2({data: options})
      }
    },
    destroyed() {
      $(this.$el).off().select2('destroy')
    }
  }
</script>
