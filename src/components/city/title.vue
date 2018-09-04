<template>
  <div class="title">
    <h2>{{text}}</h2>
  </div>
</template>

<script>
export default {
  name: 'c-title',
  props: {
    text: {
      type: String
    }
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .title
    margin: 0
    padding: .24rem .3rem
    background-color: #f5f5f5
    h2
      margin: 0
      font-size: .24rem
      color: #666
</style>
