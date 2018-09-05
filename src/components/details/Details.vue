<template>
  <div class="details-wrapper">
    <banner @openGallery='showGallery'></banner>
    <gallery :album='album'
              v-show='showFlag'
              @closeGallery='showGallery'></gallery>
  </div>
</template>

<script>
import Banner from './banner'
import Gallery from './gallery'

export default {
  name: 'Details',
  components: {
    Banner,
    Gallery
  },
  data () {
    return {
      showFlag: false,
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
  methods: {
    showGallery () {
      this.showFlag = !this.showFlag
    }
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus"></style>
