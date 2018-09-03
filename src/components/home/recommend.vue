<template>
  <div class="recommend-wrapper">
    <h1 class="title">
      <img src="http://img1.qunarzz.com/piao/fusion/1711/89/ebc329f16c55bb02.png" alt="">
      猜你喜欢
    </h1>
    <ul class="list">
      <li class="border-bottom">
        <recommend-one></recommend-one>
      </li>
    </ul>
    <p class="more border-bottom">查看所有产品</p>
  </div>
</template>

<script>
import RecommendOne from './recommend-one'

export default {
  name: 'Recommend',
  components: {
    RecommendOne
  }
}
</script>

<style scoped lang="stylus" rel='stylesheet/stylus'>
  .recommend-wrapper
    padding: .24rem 0 0 .24rem
    .title
      height: .44rem
      margin: 0 0 .26rem .08rem
      color: #212121
      font-size: .32rem
      line-height: .44rem
      img
        width: .3rem
        height: .3rem
    .list
      margin: 0
      padding: 0
      font-size: 0
    .more
      margin: 0
      padding: .2rem 0
      color: #00afc7
      font-size: .28rem
      line-height: .4rem
      text-align: center
</style>
