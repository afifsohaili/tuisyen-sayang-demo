<template>
  <div v-on:keypress="move">
    <SirAmin/>
    <Doraemon :top="topPos" :left="leftPos"/>
  </div>
</template>

<script>
import SirAmin from '~/components/SirAmin'
import Doraemon from '~/components/Doraemon'

export default {
  created: function () {
    if (!process.server) {
      window.addEventListener('keydown', this.move)
    }
  },
  components: {
    SirAmin,
    Doraemon
  },
  data: function () {
    return {
      left: 100,
      top: 50
    }
  },
  computed: {
    leftPos: function () { return this.left + 'px' },
    topPos: function () { return this.top + 'px' }
  },
  methods: {
    move: function (e) {
      if (e.key === 'ArrowUp') {
        e.preventDefault()
        this.top = this.top - 5
      } else if (e.key === 'ArrowDown') {
        e.preventDefault()
        this.top = this.top + 5
      } else if (e.key === 'ArrowLeft') {
        e.preventDefault()
        this.left = this.left - 5
      } else if (e.key === 'ArrowRight') {
        e.preventDefault()
        this.left = this.left + 5
      }

      console.log(this.top, this.left)
    }
  }
}
</script>
