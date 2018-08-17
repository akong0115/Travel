<template>
  <div class="recommend">
    <div class="recommend-title">周末去哪儿</div>
    <ul class="recommend-items">
      <li class="item border-bottom" v-for="item of list" :key="item.id">
        <div class="img-wrapper">
          <img class="item-img" :src="item.imgUrl">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .recommend
    .recommend-title
      background :#eee
      line-height :.72rem
      height :.72rem
      padding-left :.2rem
    .recommend-items
      .item
        .img-wrapper
          overflow :hidden
          width :100%
          height :0
          padding-bottom :33.9%
        .item-info
          flex :1
          padding :.1rem
          min-width :0
          .item-title
            line-height :.44rem
            height :.44rem
            ellipsis()
          .item-desc
            line-height :.44rem
            height :.44rem
            color :#ccc
            ellipsis()
</style>
