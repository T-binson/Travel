<template>
  <div class="banner-wrapper" @click='openGallery'>
    <div class="pic">
      <img src="https://img1.qunarzz.com/sight/p0/1709/41/411f234d79457081a3.img.jpg_600x330_b5e86902.jpg" alt="">
    </div>
    <div class="info">
      <div class="title">长隆野生动物世界(AAAAA景区)</div>
      <div class="total"><span class="icon">xx</span>102</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'banner',
  methods: {
    openGallery () {
      this.$emit('openGallery')
    }
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .banner-wrapper
    position: relative
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
</style>
