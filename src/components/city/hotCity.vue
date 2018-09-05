<template>
  <div class="hotcity-wrapper">
    <slot></slot>
    <ul class="cities">
      <li class="item"
          v-for="city in hotCities"
          :key="city.id"
          @click='selectCity(city.name)'><span class="city">{{city.name}}</span></li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'hotCity',
  props: {
    hotCities: {
      type: Array
    }
  },
  methods: {
    selectCity (city) {
      this.$store.dispatch('changeCity', city)
      this.$router.push('/')
    }
  }
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .hotcity-wrapper
    .cities
      overflow: hidden
      margin: 0
      padding: .2rem .3rem
      font-size: 0
      .item
        float: left
        width: 25%
        height: .6rem
        margin: 0 .2rem .2rem 0
        line-height: .6rem
        border: 1px solid #ccc
        box-sizing: border-box
        font-size: .28rem
        color: #212121
        text-align: center
        .city
          font-size: .28rem
</style>
