<template>
    <div class="header">
        <div class="header-left">
            <div class="iconfont back-icon">&#xe624;</div>
        </div>
        <div class="header-input">
            <span class="iconfont">&#xe632;</span>
            输入城市/景点/游玩主题</div>
        <router-link to="/city">
          <div class="header-right">城市
              <span class="iconfont arrow-down-icon">&#xe64a;</span>
          </div>
        </router-link>
    </div>
</template>
<script>
export default {
  name: 'HomeHeader'
}
</script>

<style lang="stylus" scoped>
    @import '~styles/varibles.styl'
    .header
        display :flex
        line-height :$headerHeight
        height :$headerHeight
        background :$bgColor
        color :#fff
        .header-left
            width :.64rem
            float :left
            .back-icon
                font-size :.4rem
                text-align :center
        .header-input
            height :.64rem
            line-height :.64rem
            flex :1
            background :#fff
            margin-top :.12rem
            margin-left :.2rem
            padding-left :.2rem
            border-radius :.1rem
            color :#ccc
        .header-right
            width :1.28rem
            float :right
            text-align :center
            color :#fff
            .arrow-down-icon
                font-size :.24rem
</style>
