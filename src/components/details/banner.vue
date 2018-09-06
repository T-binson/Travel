<template>
  <div class="banner-wrapper" @click='showGallery'>
    <header class="name"
            v-show="appear"
            :style="opacityStyle"
            @click.stop>
      <i class="icon-back"></i>
      <h1>长隆野生动物世界</h1>
    </header>
    <div class="pic">
      <img src="https://img1.qunarzz.com/sight/p0/1709/41/411f234d79457081a3.img.jpg_600x330_b5e86902.jpg" alt="">
    </div>
    <div class="info">
      <div class="title">长隆野生动物世界(AAAAA景区)</div>
      <div class="total"><span class="icon">xx</span>102</div>
    </div>
    <gallery :album='album'
              v-show='showFlag'
              @closeGallery='showGallery'></gallery>
    <div class="back" @click.stop='back' v-show="!appear">back</div>
  </div>
</template>

<script>
import Gallery from './gallery'

export default {
  name: 'banner',
  data () {
    return {
      showFlag: false,
      appear: false,
      opacityStyle: {
        opacity: 0
      },
      album: [
        {
          id: '001',
          url: 'https://img1.qunarzz.com/sight/p0/1412/66/cd09ac9548221dcc4cef8dde5913c780.water.jpg_r_800x800_bea4d4a4.jpg'
        }, {
          id: '002',
          url: 'https://img1.qunarzz.com/sight/p0/1412/d0/fb78162dda1235ed76bed4c0c637c187.water.jpg_r_800x800_7ba38130.jpg'
        }, {
          id: '003',
          url: 'https://img1.qunarzz.com/sight/p0/1412/3a/8f863cdaa5e4a44e54e507b343525557.water.jpg_r_800x800_8ac6b9d4.jpg'
        }, {
          id: '004',
          url: 'https://img1.qunarzz.com/sight/p0/1412/10/fb5c4d61b1603d4f1269cb6213354a84.water.jpg_r_800x800_92a50675.jpg'
        }, {
          id: '005',
          url: 'http://img1.qunarzz.com/sight/p0/1412/c7/0706ef15d1e5e325b83ea3c90170001a.water.jpg_r_800x800_4bba3c1e.jpg'
        }
      ]
    }
  },
  components: {
    Gallery
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
        if (top <= 200) {
          this.opacityStyle.opacity = top / 200
        }
      } else {
        this.appear = false
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this._showHeader)
  },
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
        .icon
          margin-right: .1rem
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
