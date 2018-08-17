<template>
  <ul class="dictionary">
    <li class="item" v-for="(item,key) of cities" :key="item.id">{{key}}</li>
  </ul>
</template>

<script>
export default {
  name: 'DictionaryMap',
  props: {
    cities: Object
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .dictionary
    position :absolute
    top :1.58rem
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
