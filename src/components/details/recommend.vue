<template>
  <div class="recommend-wrapper">
    <div class="title">
      <i class="icon-like">xx</i>
      <span class="text">去哪儿推荐</span>
    </div>
    <ul class="list">
      <li class="ticket-info border-top">
        <div class="desc">
          <h6 class="ticket-title">【当天可订】 广州长隆野生动物世界平日成人票</h6>
          <div class="dateTime">16:00前随买随用</div>
          <div class="notice"><span class="tag">条件退</span></div>
        </div>
        <div class="price">
          <div class="money">¥<span class="num">295</span></div>
          <div class="book-button">预订</div>
        </div>
      </li>
      <li class="ticket-info border-top">
        <div class="desc">
          <h6 class="ticket-title">野生动物世界平日家庭票2大1小或1老【惠民月促销】</h6>
          <div class="dateTime">23:45前可订明日</div>
          <div class="notice"><span class="tag">自营</span><span class="tag">不可退</span></div>
        </div>
        <div class="price">
          <div class="money">¥<span class="num">659</span></div>
          <div class="book-button">预订</div>
        </div>
      </li>
      <li class="ticket-info border-top">
        <div class="desc">
          <h6 class="ticket-title">【当天随订随用】长隆动物世界成人票-假日</h6>
          <div class="dateTime">可订9月8日</div>
          <div class="notice"><span class="tag">条件退</span></div>
        </div>
        <div class="price">
          <div class="money">¥<span class="num">339</span></div>
          <div class="book-button">预订</div>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'recommend'
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
        margin-right: .2rem
        vertical-align: top
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
