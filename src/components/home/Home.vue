<template>
  <div>
    <v-header></v-header>
    <v-slide></v-slide>
  </div>
</template>

<script>
import VHeader from './v-header'
import VSlide from './v-slide'

export default {
  name: 'Home',
  data () {
    return {
    }
  },
  components: {
    VHeader,
    VSlide
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
