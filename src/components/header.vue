<template>
  <div class="draggable-header-view"
    @mousedown="startDrag" @touchstart="startDrag"
    @mousemove="onDrag" @touchmove="onDrag"
    @mouseup="stopDrag" @touchend="stopDrag" @mouseleave="stopDrag">
      <svg class="bg" width="320" height="560">
        <path :d="headerPath" fill="#3F51B5"></path>
      </svg>
      <div class="header">
        <slot name="header"></slot>
      </div>
      <div class="content" :style="contentPosition">
        <slot name="content"></slot>
    </div>
  </div>
</template>
<script>
  import dynamics from 'dynamics.js'
  export default{
    data() {
      return {
        dragging: false,
        c: { x: 160, y: 160 },
        start: { x:0, y: 0 }
      }
    },
    computed: {
      headerPath() {
        return 'M0,0 L320,0 320,160' + 'Q' + this.c.x + ',' + this.c.y + ' 0,160'
      },
      contentPosition() {
        var dy = this.c.y - 160
        var dampen = dy > 0 ? 2 : 4
        return {
          transform: 'translate3d(0,' +dy/dampen+'+ px, 0)'
        }
      }
    },
    methods: {
      startDrag(e) {
        e = e.changedTouches ? e.changedTouches[0] : e
        this.dragging = true
        this.start.x = e.pageX
        this.start.y = e.pageY
      },
      onDrag(e) {
        e = e.changedTouches ? e.changedTouches[0] : e
        if (this.dragging) {
          this.c.x = 160 + (e.pageX - this.start.x)
          var dy = e.pageY - this.start.y
          var dampen = dy > 0 ? 1.5 : 4
          this.c.y = 160 + dy / dampen
        }
      },
      stopDrag() {
        if (this.dragging) {
          this.dragging = false
          dynamics.animate(this.c, {
            x: 160,
            y: 160
          }, {
            type: dynamics.spring,
            duration: 700,
            friction: 280
          })
        }
      }
    }
  }
</script>
