<template>
  <div class="list-wrapper">
    <slot></slot>
    <ul class="cities">
      <li class="item border-bottom" v-for="item in list" :key="item.id"><span class="city">{{item.name}}</span></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'c-list',
  props: {
    list: {
      type: Array
    }
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .list-wrapper
    .cities
      margin: 0
      padding: 0
      font-size: 0
      .item
        height: .8rem
        line-height: .8rem
        padding-left: .3rem
        font-size: .28rem
        color: #212121
        .city
          font-size: .28rem
</style>
