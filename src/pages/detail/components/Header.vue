<template>
  <div class="detail-header">
    <router-link tag="div" to="/" class="back-btn" v-show="!showFixed">
      <div class="iconfont back-icon">&#xe624;</div>
    </router-link>
    <div
      class="detial-fixed-header"
      v-show="showFixed"
      :style="opacityStyle"
    >
      <router-link tag="div" to="/" class="header-left">
          <div class="iconfont back-icon">&#xe624;</div>
      </router-link>
      <span class="hedaer-title">景点详情</span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showFixed: false,
      opacityStyle: {
        opacity: 1
      }
    }
  },
  methods: {
    handleScroll (e) {
      let scrollTop = document.documentElement.scrollTop
      if (scrollTop > 0) {
        this.showFixed = true
        this.opacityStyle.opacity = scrollTop / 45
      } else {
        this.showFixed = false
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .detail-header
    color :#fff
    .back-btn
      position :absolute
      left :.2rem
      top :.2rem
      background :rgba(0,0,0,0.6)
      padding :.16rem
      border-radius :.44rem
    .detial-fixed-header
      position :fixed
      top :0
      left :0
      right :0
      background :$bgColor
      text-align :center
      padding :.2rem
      .header-left
        float :left
</style>
