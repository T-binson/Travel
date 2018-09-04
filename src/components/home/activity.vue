<template>
  <div class="activity-wrapper" v-show='activity'>
    <div class="pic">
      <img :src="activity.imgUrl" alt="">
    </div>
    <div class="desc">
      <p class="title">{{activity.title}}</p>
      <p class="text">{{activity.text}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'activity',
  props: {
    activity: {
      type: Object,
      require: true
    }
  }
}
</script>

<style scoped lang="stylus" rel='stylesheet/stylus'>
  .activity-wrapper
    font-size: 0
    .pic
      overflow: hidden
      height: 0
      padding-bottom: 37.4375%
      img
        width: 100%
    .desc
      padding: .14rem .2rem .2rem
      .title
        margin: 0
        padding-right: 1.4rem
        color: #212121
        font-size: .28rem
        line-height: .48rem
        overflow: hidden
        white-space: nowrap
        text-overflow: ellipsis
      .text
        margin: 0
        padding-right: 1.4rem
        color: #616161
        font-size: .24rem
        line-height: .42rem
        overflow: hidden
        white-space: nowrap
        text-overflow: ellipsis
</style>
