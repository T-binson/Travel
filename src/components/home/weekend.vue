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
      activities: [
        {
          id: '001',
          title: '广州必游TOP10',
          text: '感受现代与传统相融合的广州',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/92/580e9ea4f37a1b.jpg_r_640x214_72112761.jpg'
        },
        {
          id: '002',
          title: '签到广州长隆',
          text: '来广州来长隆，就对了，就够了~',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1606/88/56f7f4bd0493fe.jpg_r_640x214_f8c0994a.jpg'
        },
        {
          id: '003',
          title: '自然户外好去处',
          text: '快快来到户外，感受花城的魅力',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/50/07fa9343791682.jpg_r_640x214_c8c3d798.jpg'
        },
        {
          id: '004',
          title: '羊城民俗风情游',
          text: '品味羊城文化，感受羊城别样风情',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/ec/902725c4d56517.jpg_r_640x214_7a74d251.jpg'
        },
        {
          id: '005',
          title: '宝贝亲子游乐地',
          text: '宝贝闲不住，我们去哪儿呀',
          imgUrl: 'http://img1.qunarzz.com/sight/source/1505/6f/bf9ef732f8ad2e.jpg_r_640x214_c759559e.jpg'
        }
      ]
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
