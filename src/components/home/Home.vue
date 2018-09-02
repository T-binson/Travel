<template>
  <div>
    <v-header></v-header>
    <v-slide></v-slide>
    <v-menu></v-menu>
  </div>
</template>

<script>
import VHeader from './v-header'
import VSlide from './v-slide'
import VMenu from './v-menu'

export default {
  name: 'Home',
  data () {
    return {
    }
  },
  components: {
    VHeader,
    VSlide,
    VMenu
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
