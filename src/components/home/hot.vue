<template>
  <div class="hot-wrapper">
    <div class="title">
      <img src="http://img1.qunarzz.com/piao/fusion/1711/16/bfbb9874e8f11402.png" alt="">
      <span class="weekrank">本周热门榜单</span>
      <span class="rank">全部榜单></span>
    </div>
    <ul class="hot-list">
      <li class="item" v-for='(item, index) in hotList' :key='item.id'>
        <div class="pic">
          <img :src="item.imgUrl" alt="">
          <span class="tag" v-if='index < 3' :class='index === 0 ? "one" : index === 1 ? "two" : "three"'>Top.{{index + 1}}</span>
        </div>
        <p class="name">{{item.name}}</p>
        <p class="price"><span><i class="currency">¥</i>{{item.price}}</span>起</p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'hot',
  data () {
    return {
      hotList: [
        {
          id: '01',
          name: '长隆野生动物世界',
          price: 210,
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1709/41/411f234d79457081a3.img.jpg_150x150_14d54b9c.jpg'
        },
        {
          id: '02',
          name: '长隆水上乐园',
          price: 120,
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1707/ab/abb70c851caaa6d8a3.img.jpg_150x150_428d0c72.jpg'
        },
        {
          id: '03',
          name: '长隆国际大马戏剧院',
          price: 325,
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1507/9e/7b5e0a44cb0310280b1aeb2a8dd94de8.water.jpg_150x150_03f4b403.jpg'
        },
        {
          id: '04',
          name: '长隆欢乐世界',
          price: 175,
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1707/47/477416df92210439a3.img.jpg_150x150_f41cda18.jpg'
        },
        {
          id: '05',
          name: '珠江夜游',
          price: 178,
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/1c/1c67791edbe2677b90.img.jpg_150x150_4eb52b11.jpg'
        },
        {
          id: '06',
          name: '广东科学中心',
          price: 30,
          imgUrl: 'http://img1.qunarzz.com/sight/p0/201212/31/309a88f591369b6893835fbb.png_150x150_5be2f7a8.png'
        },
        {
          id: '07',
          name: '广州长隆旅游度假区',
          price: 70,
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/3b/3bd311262ee06d8c90.img.jpg_150x150_97134a7a.jpg'
        },
        {
          id: '08',
          name: '广州塔',
          price: 75,
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1603/ee/ee2fb567add7969390.water.jpg_150x150_afe1378c.jpg'
        },
        {
          id: '09',
          name: '广州正佳极地海洋世界',
          price: 63,
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1709/5d/5d986aff376ff248a3.img.jpg_150x150_cb24c48b.jpg'
        },
        {
          id: '10',
          name: '广州花城汇MAG环球魔幻世界',
          price: 128,
          imgUrl: 'http://img1.qunarzz.com/sight/p0/1601/3d/3dc7f222d6bca6a790.img.jpg_150x150_a3f70573.jpg'
        }
      ]
    }
  }
}
</script>

<style scoped lang="stylus" rel='stylesheet/stylus'>
  .hot-wrapper
    .title
      position: relative
      padding: .24rem 0 .26rem
      font-size: 0
      line-height: .44rem
      img
        width: .3rem
        height: .3rem
        margin-left: .2rem
      .weekrank
        display: inline-block
        margin-left: .08rem
        color: #212121
        font-size: .32rem
      .rank
        position: absolute
        top: .24rem
        right: .32rem
        color: #616161
        font-size: .24rem
    .hot-list
      margin: 0 .24rem
      padding: 0
      overflow-x: scroll
      white-space: nowrap
      font-size: 0
      .item
        display: inline-block
        width: 2rem
        padding: .06rem 0 .2rem
        &:not(:first-child)
          margin-left: .12rem
        .pic
          position: relative
          overflow: hidden
          width: 2rem
          height: 0
          padding-bottom: 100%
          img
            width: 100%
          .tag
            position: absolute
            left: 0
            top: 0
            height: .4rem;
            width: .84rem;
            line-height: .4rem;
            text-align: center;
            color: #fff
            font-size: .24rem
            &.one
              background-color: #fa4a4d
            &.two
              background-color: #ff7f2a
            &.three
              background-color: #ffab1e
        .name
          margin: 0
          margin-top: .12rem
          color: #212121
          font-size: .24rem
          line-height: .32rem
          text-align: center
          overflow: hidden;
          width: 100%;
          white-space: nowrap;
          text-overflow: ellipsis;
        .price
          margin: 0
          color: #616161
          font-size: .24rem
          line-height: .36rem
          text-align: center
          span
            color: #ff8300
            font-size: .28rem
            .currency
              font-size: .24rem
</style>
