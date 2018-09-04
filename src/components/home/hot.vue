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
    }
  },
  props: {
    hotList: Array
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
