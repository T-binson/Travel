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
      type: Array
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
