<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.url">
          </div>
          <p class="icon-desc">{{item.text}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  computed: {
    pages () {
      var pages = []
      this.list.forEach((item, index) => {
        var page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  },
  data () {
    return {
      swiperOption: {
        autoplay: false
      }
    }
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons
    overflow :hidden
    width :100%
    height :0
    padding-bottom :50%
    .icon
      position :relative
      overflow :hidden
      width :25%
      height :0
      padding-bottom :25%
      float :left
      .icon-img
        position :absolute
        top :0
        left :0
        right :0
        bottom :.44rem
        box-sizing :border-box
        padding:.1rem
        .icon-img-content
          height :100%
          display :block
          margin :0 auto
      .icon-desc
        color :$darkTextColor
        text-align :center
        position :absolute
        left :0
        right :0
        bottom :0
        line-height :.44rem
        height :.44rem
        margin-bottom :.1rem
        ellipsis()
</style>
