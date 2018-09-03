<template>
  <div class="info-wrapper">
    <template v-for='(product, index) in products'>
      <item v-for='info in product.proInfo' :key='info.id' :info='info'></item>
      <p class="text" v-if='product.text' :key='index'>{{product.text}}</p>
    </template>
  </div>
</template>

<script>
import Item from './item'

export default {
  name: 'recommend-one',
  components: {
    Item
  },
  data () {
    return {
      products: [
        {
          proInfo: [
            {
              id: '001',
              tag: '随买随用',
              imgUrl: 'http://img1.qunarzz.com/sight/p0/1709/41/411f234d79457081a3.img.jpg_200x200_ea02ef99.jpg',
              title: '长隆野生动物世界',
              score: 5,
              rate: 75562,
              price: 210,
              address: '广州长隆野生动物世界'
            },
            {
              id: '002',
              tag: '随买随用',
              imgUrl: 'http://img1.qunarzz.com/sight/p0/1507/9e/7b5e0a44cb0310280b1aeb2a8dd94de8.water.jpg_200x200_3c429960.jpg',
              title: '长隆国际大马戏剧院',
              score: 5,
              rate: 26252,
              price: 328,
              address: '广州长隆野生动物世界'
            },
            {
              id: '003',
              tag: '可订明日',
              imgUrl: 'http://img1.qunarzz.com/sight/p0/1707/47/477416df92210439a3.img.jpg_200x200_b9e4ac2c.jpg',
              title: '长隆欢乐世界',
              score: 4,
              rate: 38348,
              price: 175,
              address: '广州长隆野生动物世界'
            },
            {
              id: '004',
              tag: '可订明日',
              imgUrl: 'http://img1.qunarzz.com/sight/p0/1707/ab/abb70c851caaa6d8a3.img.jpg_200x200_b902dd9e.jpg',
              title: '长隆水上乐园',
              score: 4,
              rate: 33917,
              price: 120,
              address: '广州长隆野生动物世界'
            }
          ],
          text: '这里最近很火哦，好多人都在点评它呢！'
        },
        {
          proInfo: [
            {
              id: '005',
              tag: '',
              imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/ee/ee3013caaa28ae7490.water.jpg_200x200_f052dfc4.jpg',
              title: '白水寨',
              score: 5,
              rate: 7841,
              price: 50.6,
              address: '增城'
            },
            {
              id: '006',
              tag: '随买随用',
              imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/3c/3c514c20a740128b90.water.jpg_200x200_c7102a23.jpg',
              title: '南沙百万葵园',
              score: 5,
              rate: 3599,
              price: 75,
              address: '南沙区'
            },
            {
              id: '007',
              tag: '可订明日',
              imgUrl: 'http://img1.qunarzz.com/sight/p0/1707/47/477416df92210439a3.img.jpg_200x200_b9e4ac2c.jpg',
              title: '长隆欢乐世界',
              score: 4,
              rate: 38348,
              price: 175,
              address: '广州长隆野生动物世界'
            },
            {
              id: '008',
              tag: '可订明日',
              imgUrl: 'http://img1.qunarzz.com/sight/p0/1411/31/74eabd4dc95afd494d92a5006c9ad4f5.water.jpg_200x200_b27fe752.jpg',
              title: '美林湖温泉',
              score: 4,
              rate: 1413,
              price: 70,
              address: '花都区'
            }
          ],
          text: '彻底放松身心、舒缓压力的无限体验'
        }
      ]
    }
  }
}
</script>

<style scoped lang="stylus" rel='stylesheet/stylus'>
  .info-wrapper
    .text
      margin-top: .4rem
      margin-right: .24rem
      margin-bottom: 0
      padding-bottom: .12rem
      color: #f55
      font-size: .24rem
      line-height: .34rem
      text-align: center
</style>
