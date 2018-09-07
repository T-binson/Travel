<template>
  <transition>
    <slot></slot>
  </transition>
</template>

<script>
export default {
  name: 'fade'
}
</script>

<style scoped lang="stylus" rel="stylesheet/stylus">
  .v-enter, .v-leave-to
    opacity: 0
  .v-enter-active, .v-leave-active
    transition: opacity .5s
</style>
