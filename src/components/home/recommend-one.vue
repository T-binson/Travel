<template>
  <div class="info-wrapper">
    <template v-for='(product, index) in products'>
      <item v-for='info in product.proInfo' :key='info.id' :info='info'></item>
      <p class="text" v-if='product.text' :key='index'>{{product.text}}</p>
    </template>
  </div>
</template>

<script>
import Item from './item'

export default {
  name: 'recommend-one',
  components: {
    Item
  },
  data () {
    return {
    }
  },
  props: {
    products: {
      type: Array
    }
  }
}
</script>

<style scoped lang="stylus" rel='stylesheet/stylus'>
  .info-wrapper
    .text
      margin-top: .4rem
      margin-right: .24rem
      margin-bottom: 0
      padding-bottom: .12rem
      color: #f55
      font-size: .24rem
      line-height: .34rem
      text-align: center
</style>
