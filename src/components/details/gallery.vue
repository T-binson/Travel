<template>
  <div class="gallery-wrapper" @click.stop='closeGallery'>
    <div class="container">
      <swiper :options="swiperOption">
        <!-- slides -->
        <swiper-slide v-for='img in album' :key="img.id">
          <img class="slide-img" :src="img.url" alt="">
        </swiper-slide>
        <!-- Optional controls -->
        <div class="swiper-pagination"  slot="pagination"></div>
      </swiper>
    </div>
  </div>
</template>

<script>
export default {
  name: 'gallery',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observer: true,
        observeParents: true
      }
    }
  },
  props: {
    album: {
      type: Array,
      default () {
        return []
      }
    }
  },
  methods: {
    closeGallery () {
      this.$emit('closeGallery')
    }
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .gallery-wrapper >>> .swiper-container
    overflow: inherit
  .gallery-wrapper
    position: fixed
    left: 0
    right: 0
    top: 0
    bottom: 0
    z-index: 99
    display: flex
    flex-direction: column
    justify-content: center
    background-color: #000
    .container
      height: 0
      width: 100%
      padding-bottom: 100%
      .slide-img
        width: 100%
        margin-top: 1.2rem
      .swiper-pagination
        color: #fff
        font-size: .24rem
        bottom: -1rem
</style>
