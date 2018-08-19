<template>
  <div class="recommend">
    <div class="recommend-title">热门推荐</div>
    <ul class="recommend-items">
      <router-link
       tag="li"
       :to="'/detail/'+item.id"
       class="item border-bottom"
       v-for="item of list"
       :key="item.id">
        <img class="item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="desc-btn">查看详情</button>
        </div>
      </router-link>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeRecommend',
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
        display :flex
        .item-img
          height :1.7rem
          width :1.7rem
          padding :.1rem
        .item-info
          flex :1
          padding :.1rem
          min-width :0
          .item-title
            line-height :.44rem
            height :.44rem
            margin-top :.1rem
            ellipsis()
          .item-desc
            line-height :.44rem
            height :.44rem
            color :#ccc
            ellipsis()
          .desc-btn
            background :#ff9300
            border-radius :.06rem
            color :#fff
            padding :0 .1rem
            line-height :.44rem
            margin-top :.1rem
</style>
