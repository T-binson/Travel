<template>
  <div class="container">
    <h3 class="index"><i class="icon-ticket"></i>{{ticket.category}}</h3>
    <ul class="tickets">
      <li class="ticket border-bottom" v-for="item in ticket.amount" :key="item.price">
        <div class="name">{{item.desc}}</div>
        <div class="price">
          <i class="currency">¥</i><span class="num">{{item.price}}</span>起<i class="icon-down">xx</i>
        </div>
      </li>
      <li class="more">
        查看剩余产品<i class="icon-down">v</i>
      </li>
    </ul>
    <gap></gap>
  </div>
</template>

<script>
import Gap from '../home/gap'

export default {
  name: 'ticket-item',
  components: {
    Gap
  },
  props: {
    ticket: {
      type: Object,
      require: true
    }
  }
}
</script>

<style scoped lang="stylus" rel='stylesheet/stylus'>
  .container
    font-size: 0
    .index
      overflow: hidden
      padding: 0 .2rem
      height: .88rem
      line-height: .88rem
      color: #333
      font-size: .32rem
      .icon-ticket
        display: inline-block
        width: .36rem
        height: .36rem
        background: url(../../assets/img/detail.png) 0 -.45rem no-repeat
        margin-right: .1rem
        background-size: .4rem 3rem
        vertical-align: text-bottom
    .tickets
      .ticket
        display: flex
        align-items: center
        padding: .24rem .2rem
        .name
          flex: 1
          color: #333
          font-size: .3rem
          line-height: .48rem
        .price
          flex: 0 0 1.8rem
          font-size: .24rem
          color: #9e9e9e
          .currency
            color: #ff9800
          .num
            margin-left: .04rem
            font-size: .4rem
            color: #ff9800
          .icon-down
            color: #bbb
      .more
        height: .8rem
        line-height: .8rem
        text-align: center
        color: #616161
        font-size: .28rem
        .icon-down
          margin-left: .1rem
          font-size: .2rem
</style>
