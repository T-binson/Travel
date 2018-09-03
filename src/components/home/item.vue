<template>
  <div class="item-wrapper border-bottom">
    <div class="pic">
      <span class="tag" v-if='info.tag' :class='info.tag === "随买随用" ? "oringe" : "blue"'>{{info.tag}}</span>
      <img :src="info.imgUrl" alt="">
    </div>
    <div class="info">
      <p class="title">{{info.title}}</p>
      <p class="review">
        <template v-for='star in info.score'>
          <span class="star" :key='star'><img src="../../assets/img/1star.png" alt=""></span>
        </template>
        <span class="comment">{{info.rate}}条评论</span>
      </p>
      <p class="price"><span>¥{{info.price}}</span>起</p>
      <div class="address">{{info.address}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'item',
  props: {
    info: {
      type: Object,
      require: true
    }
  }
}
</script>

<style scoped lang="stylus">
  .item-wrapper
    display: flex
    padding: .2rem 0
    font-size: 0
    .pic
      position: relative
      flex: 0 0 2rem
      margin-right: .22rem
      .tag
        position: absolute
        left: 0
        top: 0
        width: 1.02rem
        height: .38rem
        line-height: .38rem
        text-indent: .04rem
        font-size: .2rem
        color: #fff
        border-bottom-right-radius: .2rem
        &.oringe
          background-color: #ff8f09
        &.blue
          background-color: #00afc7
      img
        width: 2rem
        height: 2rem
    .info
      position: relative
      flex: 1
      .title
        margin-top: .26rem
        margin-bottom: 0
        font-size: .32rem
        color: #212121
        line-height: .44rem
      .review
        margin-top: .14rem
        .star
          font-size: .28rem
        .comment
          margin-left: .2rem
          color: #616161
          font-size: .24rem
          line-height: .34rem
      .price
        line-height: .4rem
        font-size: .24rem
        margin-top: .22rem
        margin-bottom: 0
        span
          font-size: .4rem
          color: #ff8300
      .address
        position: absolute
        right: .24rem
        bottom: 0.12rem
        width: 1.2rem
        color: #616161
        font-size: .24rem
        line-height: .4rem
        overflow: hidden
        white-space: nowrap
        text-overflow: ellipsis
        text-align: right
</style>
