<template>
  <div class="detial">
    <banner></banner>
    <detail-header></detail-header>
    <div class="block"></div>
  </div>
</template>

<script>
import Banner from './components/Banner'
import DetailHeader from './components/Header'
export default {
  naem: 'Detail',
  components: {
    Banner,
    DetailHeader
  }
}
</script>

<style lang="stylus" scoped>
  .block
    height :20rem
</style>
