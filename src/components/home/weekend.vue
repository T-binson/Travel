<template>
  <div class="weekend-wrapper">
    <h2 class="title">周末去哪儿</h2>
    <template v-for='activity in activities'>
      <activity :activity='activity' :key='activity.id'></activity>
    </template>
  </div>
</template>

<script>
import Activity from './activity'

export default {
  name: 'weekend',
  components: {
    Activity
  },
  data () {
    return {
    }
  },
  props: {
    activities: {
      type: Array
    }
  }
}
</script>

<style scoped lang="stylus" rel='stylesheet/stylus'>
  .weekend-wrapper
    font-size: 0
    .title
      margin: 0
      height: .8rem
      padding-left: .26rem
      line-height: .8rem
      font-size: .28rem
      color: #212121
      background-color: #f5f5f5
</style>
