<template>
  <div>
    <v-header></v-header>
    <v-slide></v-slide>
    <v-menu></v-menu>
    <gap></gap>
    <hot></hot>
    <gap></gap>
    <recommend></recommend>
    <weekend></weekend>
  </div>
</template>

<script>
import VHeader from './v-header'
import VSlide from './v-slide'
import VMenu from './v-menu'
import Recommend from './recommend'
import Weekend from './weekend'
import Hot from './hot'
import Gap from './gap'

export default {
  name: 'Home',
  data () {
    return {
    }
  },
  components: {
    VHeader,
    VSlide,
    VMenu,
    Recommend,
    Weekend,
    Hot,
    Gap
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
