<template>
  <div class="header">
    <div class="back">
      <i class="icon-back"></i>
    </div>
    <div class="input">
      <input type="text" class="search" placeholder="输入城市/景点/游玩主题">
    </div>
    <div class="city" @click="selectCity">
      <!-- <span>{{this.$store.state.city}}</span> -->
      <span>{{this.city}}</span>
      <i class="icon-triangle-down"></i>
    </div>
  </div>
</template>

<script>
import {mapState} from 'vuex'

export default {
  name: 'v-header',
  /* props: {
    city: {
      type: String
    }
  }, */
  methods: {
    selectCity () {
      this.$router.push('/city')
    }
  },
  computed: {
    ...mapState(['city'])
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
@import '../../assets/css/icon-font'
.header
  line-height: .86rem
  width: 100%
  display: flex
  background-color: #00bcd4
  color: #fff
  div
    height: 100%
  .back
    flex: 0 0 .64rem
    font-size: .32rem;
  .input
    flex: 1
    font-size: .28rem
    color: #ccc
    .search
      background-color: #fff
      width: 100%
      line-height: 100%
      height: .6rem
      margin: 0 .12rem
      padding-left: .12rem
      box-sizing: border-box
      border-radius: .1rem
      outline: none
      border: none
  .city
    min-width: 1.04rem
    padding: 0 .1rem
    text-align: center
    font-size: .24rem
    span
      padding: 0 .1rem
</style>
