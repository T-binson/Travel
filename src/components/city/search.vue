<template>
  <div class="search">
    <input type="text" placeholder="请输入城市名或拼音">
  </div>
</template>

<script>
export default {
  name: 'search'
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .search
    height: .72rem
    padding: 0 .1rem
    background-color: #00bcd4
    font-size: .32rem
    input
      width: 100%
      height: .62rem
      padding: 0 .1rem
      box-sizing: border-box
      border: none
      outline: none
      line-height: .62rem
      text-align: center
      border-radius: .06rem
      color: #666
</style>
