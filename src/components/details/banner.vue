<template>
  <div class="banner-wrapper" @click='showGallery'>
    <header class="name"
            v-show="appear"
            :style="opacityStyle"
            @click.stop>
      <i class="icon-back">back</i>
      <h1>长隆野生动物世界</h1>
    </header>
    <div class="pic">
      <img :src="banner.poster" alt="">
    </div>
    <div class="info">
      <div class="title">{{banner.title}}</div>
      <div class="total"><span class="icon-thumbnail"></span>{{thumbnails.amount}}</div>
    </div>
    <fade>
      <gallery :album='thumbnails.album'
              v-show='showFlag'
              @closeGallery='showGallery'></gallery>
    </fade>
    <div class="back" @click.stop='back' v-show="!appear">back</div>
  </div>
</template>

<script>
import Gallery from './gallery'
import Fade from '../animation/fade'

export default {
  name: 'banner',
  data () {
    return {
      showFlag: false,
      appear: false,
      opacityStyle: {
        opacity: 0
      },
      thumbnails: {}
    }
  },
  props: {
    banner: {
      type: Object,
      require: true
    }
  },
  components: {
    Gallery,
    Fade
  },
  methods: {
    showGallery () {
      this.showFlag = !this.showFlag
    },
    back () {
      this.$router.push('/')
    },
    _showHeader () {
      const top = document.documentElement.scrollTop
      if (top > 40) {
        this.appear = true
        const opacity = top / 200
        this.opacityStyle.opacity = opacity > 1 ? 1 : opacity
      } else {
        this.appear = false
      }
    }
  },
  updated () {
    this.thumbnails = this.banner.thumbnails
    window.addEventListener('scroll', this._showHeader)
  },
  /* activated () {
    window.addEventListener('scroll', this._showHeader)
  }, */
  deactivated () {
    window.removeEventListener('scroll', this._showHeader)
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .banner-wrapper
    position: relative
    .name
      font-size: 0
      background-color: #00bcd4
      position: fixed
      left: 0
      top: 0
      z-index: 90
      height: .88rem
      width: 100%
      .icon-back
        position: absolute
        left: 0
        top: 0
        width: .8rem
        height: .88rem
        font-size: .24rem
      h1
        height: .88rem
        line-height: .88rem
        margin: 0 1rem
        font-size: .32rem
        color: #fff
        text-align: center
        overflow: hidden
        white-space: nowrap
        text-overflow: ellipsis
    .pic
      overflow: hidden
      height: 0
      width: 100%
      padding-bottom: 55%
      img
        width: 100%
    .info
      display: flex
      position: absolute
      left: 0
      right: 0
      bottom: .2rem
      min-height: .4rem
      padding: 0 .2rem
      &::after
        content: ''
        position: absolute
        top: .2rem
        left: 0
        width: 100%
        min-height: .4rem
        background-image: linear-gradient(to bottom, rgba(0, 0, 0, 0), rgba(0, 0, 0, .8))
      .title
        flex: 1
        font-size: .36rem
        color: #fff
        line-height: .4rem
      .total
        width: 1.2rem
        height: .4rem
        background-color: rgba(0, 0, 0, .5)
        border-radius: .2rem
        font-size: .24rem
        color: #fff
        line-height: .4rem
        text-align: center
        .icon-thumbnail
          margin-right: .1rem
          background: url(/static/img/detail.ee758fd.png) 0 -2.2rem no-repeat
          background-size: 0.4rem 3rem
          display: inline-block
          width: .3rem
          height: .3rem
          vertical-align: top
    .back
      position: absolute
      left: .1rem
      top: .1rem
      width: .72rem
      height: .72rem
      border-radius: 50%
      background-color: #000
      font-size: .36rem
      line-height: .72rem
      opacity: .5
</style>
