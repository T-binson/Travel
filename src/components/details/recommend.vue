<template>
  <div class="recommend-wrapper">
    <div class="title">
      <i class="icon-like"></i>
      <span class="text">去哪儿推荐</span>
    </div>
    <ul class="list">
      <li class="ticket-info border-top" v-for="(recommend, index) in recommendList" :key="index">
        <div class="desc">
          <h6 class="ticket-title">{{recommend.desc}}</h6>
          <div class="dateTime">{{recommend.dateTime}}</div>
          <div class="notice"><span class="tag" v-for="(tag, index) in recommend.tags" :key="index">{{tag}}</span></div>
        </div>
        <div class="price">
          <div class="money">¥<span class="num">{{recommend.price}}</span></div>
          <div class="book-button">预订</div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'recommend',
  props: {
    recommendList: {
      type: Array,
      require: true
    }
  }
}
</script>

<style scoped lang="stylus" rel='stylesheet/stylus'>
  .recommend-wrapper
    padding-left: .2rem
    margin-bottom: .2rem
    .title
      height: .88rem
      line-height: .88rem
      font-size: 0
      .icon-like
        font-size: .24rem
        margin-right: .1rem
        background: url(/static/img/detail.ee758fd.png) 0 -2.6rem no-repeat
        background-size: 0.4rem 3rem
        display: inline-block
        width: .4rem
        height: .4rem
      .text
        font-size: .32rem
        color: #333
    .list
      .ticket-info
        display: flex
        padding: .2rem .2rem .24rem 0
        .desc
          flex: 1
          .ticket-title
            margin-right: .1rem
            line-height: .52rem
            font-size: .3rem
            color: #616161
          .dateTime
            line-height: .32rem
            color: #616161
            font-size: .24rem
            overflow: hidden
            white-space: nowrap
            text-overflow: ellipsis
          .notice
            overflow: hidden
            white-space: nowrap
            font-size: 0
            .tag
              display: inline-block
              margin-top: .08rem
              padding: 0 .04rem
              height: .32rem
              line-height: .32rem
              color: #00afc7
              font-size: .2rem
              border: 1px solid #e0e0e0
              &:not(last-child)
                margin-right: .1rem
        .price
          flex: 0 0 1.8rem
          display: flex
          flex-direction: column
          justify-content: center
          padding-left: .2rem
          .money
            font-size: .24rem
            line-height: .28rem
            text-align: center
            color: #ff9800
            .num
              margin-left: .04rem
              font-size: .4rem
              line-height: .4rem
          .book-button
            height: .6rem
            line-height: .6rem
            font-size: .28rem
            color: #fff
            border-radius: .08rem
            text-align: center
            background-image: linear-gradient(130deg, #ffab1e 37%, #ff8c12 100%)
</style>
