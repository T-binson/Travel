<template>
  <div class="slide-wrapper">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for='item in slidePic' :key="item.id">
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
    slidePic: {
      type: Array,
      default () {
        return [
          {
            id: '001',
            url: 'http://img1.qunarzz.com/piao/fusion/1805/e8/14b75b1c81fbe702.jpg_750x200_e6d4f1f1.jpg'
          },
          {
            id: '002',
            url: 'http://img1.qunarzz.com/piao/fusion/1808/18/2dbce82b07a23402.jpg_750x200_14356b03.jpg'
          },
          {
            id: '003',
            url: 'http://img1.qunarzz.com/piao/fusion/1808/b0/a123fba6d7e3dd02.jpg_750x200_1425741a.jpg'
          },
          {
            id: '004',
            url: 'http://img1.qunarzz.com/piao/fusion/1807/66/e5a5cec881702f02.jpg_750x200_67bb5691.jpg'
          }
        ]
      }
    }
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
