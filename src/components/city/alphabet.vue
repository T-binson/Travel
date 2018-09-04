<template>
  <div class="alphabet">
    <ul class="list">
      <li class="letter"
          v-for="(item, index) in alphabet"
          :key="index"
          ref="letter"
          @click='selectItem(item)'
          @touchstart='touchStart'
          @touchmove='touchMove'
          @touchend="touchEnd">{{item}}</li>
    </ul>
  </div>
</template>
<script>
const HEIGHT = 18
const TOPHEIGHT = 112

export default {
  name: 'alphabet',
  props: {
    alphabet: {
      type: Array
    }
  },
  data () {
    return {
      touchStatus: false,
      distance: 0,
      startY: 0,
      index: 0,
      timer: null
    }
  },
  /* computed: {
    startY () {
      return this.$refs.letter[0].offsetTop + TOPHEIGHT
    }
  }, */
  updated () {
    this.startY = this.$refs.letter[0].offsetTop + TOPHEIGHT
  },
  methods: {
    selectItem (item) {
      this.$emit('select', item)
    },
    touchStart () {
      this.touchStatus = true
    },
    touchMove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        // jieliu
        this.timer = setTimeout(() => {
          this.distance = e.touches[0].pageY - this.startY
          this.index = Math.floor(this.distance / HEIGHT)
          if (this.index >= 0 && this.index < this.alphabet.length) {
            this.$emit('select', this.index)
          }
        }, 16)
      }
    },
    touchEnd (e) {
      this.touchStatus = false
    }
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .alphabet
    margin: 0
    .list
      display: flex
      flex-direction: column
      justify-content: center
      position: absolute
      right: 0
      top: 2.24rem
      bottom: 0
      margin: 0
      padding: 0
      .letter
        font-size: .28rem
        line-height: .36rem
        color: #00bcd4
        text-align: center
</style>
