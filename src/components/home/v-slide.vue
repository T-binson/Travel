<template>
  <div class="slide-wrapper">
    <swiper :options="swiperOption" v-if='banner.length'>
      <!-- slides -->
      <swiper-slide v-for='item in banner' :key="item.id">
        <img class="slide-img" :src="item.url" alt="">
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'v-slide',
  data () {
    return {
      swiperOption: {
        autoplay: 3000,
        loop: true,
        pagination: '.swiper-pagination'
      }
    }
  },
  props: {
    banner: {
      type: Array
    }
  },
  activated () {
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
.slide-wrapper >>> .swiper-pagination-bullet-active
  background-color: #fff
.slide-wrapper
  width: 100%
  height: 0
  overflow: hidden
  padding-bottom: 26.67%
  background-color: #eee
  .slide-img
    width: 100%
</style>
