<template>
  <ul class="dictionary">
    <li class="item">A</li>
    <li class="item">B</li>
    <li class="item">C</li>
    <li class="item">D</li>
    <li class="item">E</li>
  </ul>
</template>

<script>
export default {
  name: 'DictionaryMap'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .dictionary
    position :fixed
    top :0
    bottom :0
    right :0
    display :flex
    flex-direction :column
    justify-content :center
    width :.4rem
    .item
      color :$bgColor
      line-height :.4rem
</style>
