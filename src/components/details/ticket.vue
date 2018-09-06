<template>
  <div class="ticket-wrapper">
    <header class="tab">
      <div class="btn active">门票</div>
      <div class="btn">一日游</div>
    </header>
    <ticket-item></ticket-item>
  </div>
</template>

<script>
import TicketItem from './ticket-item'

export default {
  name: 'ticket',
  components: {
    TicketItem
  }
}
</script>

<style scoped lang="stylus" rel='stylesheet/stylus'>
  .ticket-wrapper
    font-size: 0
    .tab
      display: flex
      justify-content: space-around
      height: .92rem
      line-height: .92rem
      .btn
        padding: 0 .38rem
        font-size: .32rem
        color: #212121
        &.active
          border-bottom: .04rem solid #00bcd4
</style>
