<template>
  <div>
    <!-- <v-header :city='city'></v-header> -->
    <v-header></v-header>
    <v-slide :banner="banner"></v-slide>
    <v-menu :menu='menu'></v-menu>
    <gap></gap>
    <hot :hotList='hotList'></hot>
    <gap></gap>
    <recommend :products='products'></recommend>
    <weekend :activities='activities'></weekend>
  </div>
</template>

<script>
import VHeader from './v-header'
import VSlide from './v-slide'
import VMenu from './v-menu'
import Recommend from './recommend'
import Weekend from './weekend'
import Hot from './hot'
import Gap from './gap'
import axios from 'axios'
import {mapState} from 'vuex'

const ERR_OK = 0

export default {
  name: 'Home',
  data () {
    return {
      // city: '',
      banner: [],
      products: [],
      menu: [],
      activities: [],
      hotList: [],
      lastCity: ''
    }
  },
  components: {
    VHeader,
    VSlide,
    VMenu,
    Recommend,
    Weekend,
    Hot,
    Gap
  },
  mounted () {
    this.lastCity = this.city
    this._getInfo()
  },
  activated () {
    if (this.lastCity !== this.city) {
      this.lastCity = this.city
      this._getInfo()
    }
  },
  computed: {
    ...mapState(['city'])
  },
  methods: {
    _getInfo () {
      axios.get('/api/index.json?city=' + this.city).then(this.normalize)
    },
    normalize (res) {
      if (res.data.code === ERR_OK && res.data.data) {
        let data = res.data.data
        // this.city = data.city
        this.banner = data.banner
        this.products = data.products
        this.menu = data.menu
        this.activities = data.activities
        this.hotList = data.hotList
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
