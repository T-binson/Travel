<template>
  <header>
    <div class="title-wrapper border-bottom">
      <router-link to='/'><i class="back">back</i></router-link>
      <h2 class="title">城市选择</h2>
    </div>
    <div class="tab-wrapper">
      <div class="tab">
        <span class="domestic">境内</span><span class="foreign">境外·港澳台</span>
      </div>
    </div>
  </header>
</template>
<script>
export default {
  name: 'c-header'
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  header
    position: relative
    margin: 0
    font-size: 0
    background-color: #00bcd4
    .title-wrapper
        height: .68rem
      .back
        position: absolute
        left: 0
        top: 0
        width: .8rem
        height: .88rem
        line-height: .88rem
        font-size: .32rem
        color: #fff
      .title
        margin: 0
        font-size: .32rem
        text-align: center
        line-height: .88rem
        color: #fff
    .tab-wrapper
      margin: 0
      padding: .2rem 1rem
      .tab
        margin: 0
        border: 1px solid #fff
        border-radius: .03rem
        color: #fff
        box-sizing: border-box
        font-size: .28rem
        .domestic, .foreign
          display: inline-block
          width: 50%
          text-align: center
          line-height: .4rem
        .domestic
          background-color: #fff
          color: #00bcd4
</style>
