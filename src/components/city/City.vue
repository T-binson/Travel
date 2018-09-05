<template>
  <div class="city-wrapper">
    <div class="top">
      <c-header></c-header>
      <search :cities='lists'></search>
    </div>
    <div class="main" ref='main'>
      <div class="main-wrapper">
        <div class="location">
          <c-title :text='t1'></c-title>
          <ul class="cur-wrapper">
            <li class="cur">
              <span>城市</span>
            </li>
          </ul>
        </div>
        <hot-city :hotCities="hotCities">
          <c-title :text="t2"></c-title>
        </hot-city>
        <div class="city-list">
          <c-list v-for="item in lists"
                  :list="item.list"
                  :key="item.letter">
            <c-title :text='item.letter' ref="letter"></c-title>
          </c-list>
        </div>
      </div>
    </div>
    <alphabet :alphabet='alphabet' @select="selectItem"></alphabet>
  </div>
</template>
<script>
import CHeader from './c-header'
import Search from './search'
import CTitle from './title'
import HotCity from './hotCity'
import CList from './c-list'
import Alphabet from './alphabet'
import BScroll from 'better-scroll'
import axios from 'axios'

const ERR_OK = 0

export default {
  name: 'City',
  components: {
    CHeader,
    Search,
    CTitle,
    Alphabet,
    HotCity,
    CList
  },
  data () {
    return {
      t1: '当前位置',
      t2: '热门城市',
      hotCities: [],
      lists: [],
      alphabet: [],
      letter: ''
    }
  },
  methods: {
    selectItem (item) {
      let index = 0
      if (typeof item === 'string') {
        if (this.letter === item) { return }
        this.letter = item
        if (!this.scroll) {
          this.scroll = new BScroll(this.$refs.main)
        }
        index = this.lists.findIndex((item) => {
          return item.letter === this.letter
        })
      } else {
        index = item
      }
      this.scroll.scrollToElement(this.$refs.letter[index].$el, 500)
    },
    _getCity () {
      axios.get('/api/city.json').then(this._normalizeData)
    },
    _normalizeData (res) {
      if (res.data.code === ERR_OK && res.data.data) {
        let data = res.data.data
        this.hotCities = data.hotCity
        this.lists = data.cities
        this.alphabet = data.alphabet
      }
    }
  },
  mounted () {
    this.scroll = new BScroll('.main')
    this._getCity()
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .city-wrapper
    .main
      position: absolute
      top: 2.24rem
      left: 0
      right: 0
      bottom: 0
      overflow: hidden
      .location
        margin: 0
        .cur-wrapper
          margin: 0
          height: .9rem
          padding: .15rem .3rem
          box-sizing: border-box
          .cur
            width: 25%
            height: .6rem
            line-height: .6rem
            border: 1px solid #ccc
            box-sizing: border-box
            font-size: .28rem
            color: #00bcd4
            text-align: center
</style>
