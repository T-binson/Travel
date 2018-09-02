<template>
  <div class="menu-wrapper border border-bottom">
    <swiper :options="swiperOption">
      <!-- slides -->
      <swiper-slide v-for='(page, index) in pages' :key="index">
        <div class="item-wrapper" v-for='item in page' :key='item.id'>
          <div class="icon">
            <img :src="item.iconUrl" alt="">
          </div>
          <p class="desc">{{item.title}}</p>
        </div>
      </swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination dot"  slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'v-menu',
  props: {
    menu: {
      type: Array,
      default () {
        return [
          {
            id: '001',
            title: '景点门票',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png'
          },
          {
            id: '002',
            title: '广州必游',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png'
          },
          {
            id: '003',
            title: '动植物园',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png'
          },
          {
            id: '004',
            title: '游乐场',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/8246f27355943202.png'
          },
          {
            id: '005',
            title: '珠江夜游',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/89/55083b0f1951f302.png'
          },
          {
            id: '006',
            title: '夏日玩水',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png'
          },
          {
            id: '007',
            title: '城市观光',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b6/37560ece9c62b502.png'
          },
          {
            id: '008',
            title: '网红打卡',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1808/8d/747c9a29b8dba402.png'
          },
          {
            id: '009',
            title: '玩转长隆',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/b1/528a9e80403b8c02.png'
          },
          {
            id: '010',
            title: '全部玩乐',
            iconUrl: 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png'
          }
        ]
      }
    }
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination'
      }
    }
  },
  methods: {
    _normalizeMenu (arr) {
      /* let ret = {}
      const items = 8
      let page = Math.floor(arr.length / items)
      for (let i = 0; i <= page; i++) {
        if (!ret[i]) {
          ret[i] = []
        }
      }
      for (let key in ret) {
        if (ret.hasOwnProperty(key)) {
          ret[key] = arr.splice(0, items)
        }
      }
      this.ret = ret */
    }
  },
  computed: {
    pages () {
      let pages = []
      this.menu.forEach((item, index) => {
        let page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .menu-wrapper
    overflow: hidden
    height: 0
    padding-bottom: 50%
    padding-top: .1rem
    font-size: 0
    .swiper-container
      height: 0;
      padding-bottom: 50%
    .item-wrapper
      float: left
      width: 25%
      height: 1.5rem
      padding-top: .1rem
      .icon
        width: 1.1rem
        height: 1.1rem
        margin: 0 auto
        text-align: center
        img
          width: 1.1rem
          height: 1.1rem
      .desc
        margin: .1rem 0px 0px 0px
        text-align: center
        font-size: .28rem
        color: #212121
        overflow: hidden
        white-space: nowrap
        text-overflow: ellipsis
    .dot
      height: .16rem
    .dot >>> span.swiper-pagination-bullet
        width: 6px
        height: 6px
        margin-right: 4px
</style>
