<template>
  <div class="header">
    <router-link to="/">
      <div class="iconfont back-icon">&#xe624;</div>
    </router-link>
    城市选择
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header
    position :relative
    height :$headerHeight
    line-height :$headerHeight
    background :$bgColor
    text-align :center
    color :#fff
    .back-icon
      position :absolute
      left :0
      font-size :.4rem
      color :#fff
</style>
