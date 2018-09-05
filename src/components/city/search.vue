<template>
  <div class="search">
    <div class="search-box">
      <input type="text" placeholder="请输入城市名或拼音" v-model='keywords'>
    </div>
    <div class="search-content" v-show='keywords' ref='searchWrapper'>
      <ul class="search-list">
        <li class="item border-bottom"
            v-for='(item, index) in results'
            :key='index'
            @click="selectCity(item.name)">{{item.name}}</li>
        <li class="item border-bottom" v-show='!results.length'>没有找到匹配的数据</li>
      </ul>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
import {mapMutations} from 'vuex'

export default {
  name: 'search',
  data () {
    return {
      keywords: '',
      results: [],
      timer: null
    }
  },
  props: {
    cities: {
      type: Array
    }
  },
  watch: {
    keywords () {
      if (!this.keywords) {
        this.results = []
        return
      }
      if (this.timer) {
        clearTimeout(this.timer)
      }
      const list = []
      this.timer = setTimeout(() => {
        this.cities.forEach((item) => {
          item.list.forEach((city) => {
            if (city.name.indexOf(this.keywords) > -1 || city.spell.indexOf(this.keywords) > -1) {
              list.push(city)
            }
          })
        })
      }, 200)
      this.results = list
      // this.scroll.refresh()
    }
  },
  methods: {
    selectCity (city) {
      // this.$store.commit('changeCity', city)
      this.changeCity(city)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  mounted () {
    this.$nextTick(() => {
      this.scroll = new BScroll(this.$refs.searchWrapper)
    })
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .search
    .search-box
      height: .72rem
      padding: 0 .1rem
      background-color: #00bcd4
      font-size: .32rem
      input
        width: 100%
        height: .62rem
        padding: 0 .1rem
        box-sizing: border-box
        border: none
        outline: none
        line-height: .62rem
        text-align: center
        border-radius: .06rem
        color: #666
    .search-content
      position: absolute
      left: 0
      top: 2.24rem
      right: 0
      bottom: 0
      z-index: 1
      width: 100%
      overflow: hidden
      background-color: #fff
      .search-list
        margin: 0
        padding: 0
        font-size: 0
        .item
          padding: 0 .2rem
          font-size: .28rem
          line-height: .48rem
          color: #212121
</style>
