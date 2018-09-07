  <template>
  <div class="details-wrapper">
    <banner :banner="banner"></banner>
    <div class="baseInfo">
      <div class="message-wrapper">
        <div class="left border-right">
          <p class="top"><span class="score">{{baseInfo.score}}</span>分<span class="desc">{{baseInfo.keyword}}</span></p>
          <p class="bot"><span class="comment">{{baseInfo.rate}}条评论</span><span class="tips">{{baseInfo.tips}}条攻略</span></p>
          <i class="icon-arrow">xx</i>
        </div>
        <div class="right">
          <p class="title">景点简介</p>
          <p class="text">开放时间、贴士</p>
          <i class="icon-arrow">xx</i>
        </div>
      </div>
      <div class="address-wrapper border-top">
        <i class="icon-bubble"></i>
        <span class="address">{{baseInfo.address}}</span>
        <i class="icon-arrow">x</i>
      </div>
    </div>
    <gap></gap>
    <div class="bulletin">
      <i class="icon-horn">xx</i>
      <span class="content">{{bulletin}}</span>
      <i class="icon-arrow">xx</i>
    </div>
    <gap></gap>
    <recommend :recommendList="recommendList"></recommend>
    <gap></gap>
    <ticket :tickets="tickets"></ticket>
  </div>
</template>

<script>
import Banner from './banner'
import Gap from '../home/gap'
import Recommend from './recommend'
import Ticket from './ticket'
import axios from 'axios'

const ERR_OK = 0

export default {
  name: 'Details',
  components: {
    Banner,
    Gap,
    Recommend,
    Ticket
  },
  data () {
    return {
      recommendList: [],
      banner: {},
      tickets: [],
      baseInfo: {},
      bulletin: ''
    }
  },
  methods: {
    _getData () {
      axios.get('/api/details.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this._normalize)
    },
    _normalize (res) {
      if (res.data.code === ERR_OK && res.data.data) {
        const data = res.data.data
        this.banner = data.banner
        this.recommendList = data.recommend
        this.tickets = data.tickets
        this.baseInfo = data.baseInfo
        this.bulletin = data.bulletin
      }
    }
  },
  mounted () {
    this._getData()
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .details-wrapper
    .baseInfo
      padding: .1rem .2rem 0 .2rem
      margin-bottom: .1rem
      .message-wrapper
        display: flex
        padding: .1rem 0 .2rem
        .left
          flex: 1
          position: relative
          .top
            font-size: .28rem
            line-height: .48rem
            color: #ff8300
            .score
              font-size: .44rem
              line-height: .44rem
            .desc
              margin-left: .2rem
          .bot
            color: #9e9e9e
            line-height: .32rem
            font-size: .24rem
            .comment
              margin-right: .2rem
          .icon-arrow
            position: absolute
            right: .2rem
            top: .3rem
            font-size: .24rem
            color: #9e9e9e
        .right
          flex: 1
          position: relative
          .title
            font-size: .28rem
            color: #212121
            line-height: .48rem
            padding-left: .3rem
          .text
            color: #9e9e9e
            font-size: .24rem
            padding-left: .3rem
          .icon-arrow
            position: absolute
            right: .2rem
            top: .3rem
            font-size: .24rem
            color: #9e9e9e
      .address-wrapper
        padding: .2rem 0
        line-height: .36rem
        color: #212121
        font-size: 0
        .icon-bubble
          display: inline-block
          font-size: .24rem
          margin-right: .2rem
          background: url(/static/img/detail.ee758fd.png) 0 -1.8rem no-repeat
          background-size: 0.4rem 3rem
          width: .3rem
          height: .36rem
          vertical-align: top
        .address
          font-size: .28rem
          padding-right: .56rem
          display: inline-block
          overflow: hidden
          white-space: nowrap
          text-overflow: ellipsis
          max-width: 6rem
        .icon-arrow
          display: inline-block
          font-size: .24rem
          vertical-align: top
    .bulletin
      height: .88rem
      padding-left: .23rem
      background-color: #fff5e5
      color: #ff8300
      line-height: .88rem
      font-size: 0
      .icon-horn
        display: inline-block
        vertical-align: top
        margin-right: .2rem
        font-size: .24rem
      .content
        display: inline-block
        max-width: 6rem
        padding-right: .6rem
        overflow: hidden
        white-space: nowrap
        text-overflow: ellipsis
        font-size: .28rem
      .icon-arrow
        display: inline-block
        vertical-align: top
        font-size: .24rem
</style>
