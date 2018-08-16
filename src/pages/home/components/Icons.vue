<template>
  <div class="icons">
    <swiper>
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
  data () {
    return {
      iconsList: [
        {
          id: 1,
          url: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
          text: '景点门票'
        },
        {
          id: 2,
          url: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
          text: '一日游'
        },
        {
          id: 3,
          url: 'http://img1.qunarzz.com/piao/fusion/1804/ff/fdf170ee89594b02.png',
          text: '杭州必游'
        },
        {
          id: 4,
          url: 'http://img1.qunarzz.com/piao/fusion/1803/75/eca3ce656c886502.png',
          text: '漂流'
        },
        {
          id: 5,
          url: 'http://img1.qunarzz.com/piao/fusion/1803/6a/45f595250c73d102.png',
          text: '夏日玩水'
        },
        {
          id: 6,
          url: 'http://img1.qunarzz.com/piao/fusion/1803/17/99402a22ce4af302.png',
          text: '西湖'
        },
        {
          id: 7,
          url: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
          text: '宋城千古情'
        },
        {
          id: 8,
          url: 'http://img1.qunarzz.com/piao/fusion/1804/95/8d02011d149bdb02.png',
          text: '汽车票'
        },
        {
          id: 9,
          url: 'http://img1.qunarzz.com/piao/fusion/1803/e3/67df61427c8e1302.png',
          text: '宋城千古情'
        },
        {
          id: 10,
          url: 'http://img1.qunarzz.com/piao/fusion/1804/95/8d02011d149bdb02.png',
          text: '汽车票'
        }
      ]
    }
  },
  computed: {
    pages () {
      var pages = []
      this.iconsList.forEach((item, index) => {
        var page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
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
        ellipsis()
</style>
