<template>
  <div>
    <div class="banner" @click="openGallery">
        <img
        class="banner-img"
        src="//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg"
        >
        <div class="banner-desc">
          <div class="banner-album">
            <span class="iconfont icon-album">&#xe613;</span>
            <p class="photo-num">10</p>
          </div>
          <h1 class="banner-title">故宫（AAAAA景区）</h1>
        </div>
    </div>
    <banner-gallery :imgs="imgs" @closeGallery="closeGallery" v-show="showGallery" :update="update"></banner-gallery>
  </div>
</template>

<script>
import BannerGallery from 'common/gallery/Gallery'

export default {
  naem: 'Banner',
  components: {
    BannerGallery
  },
  data () {
    return {
      imgs: [
        'http://img1.qunarzz.com/sight/p55/201211/04/fbcab3e5d6479ce893835fbb.jpg_r_800x800_6360f514.jpg',
        'http://img1.qunarzz.com/wugc/p123/201211/19/a2045d091f02b25493835fbb.png_r_800x800_c59f0eba.png'
      ],
      showGallery: false
    }
  },
  computed: {
    update () {
      return this.showGallery
    }
  },
  methods: {
    closeGallery () {
      this.$nextTick(() => {
        this.showGallery = false
      })
    },
    openGallery () {
      this.$nextTick(() => {
        this.showGallery = true
      })
    }
  }
}
</script>

<style lang="stylus" scoped>
.banner
  position :relative
  .banner-img
    width :100%
  .banner-desc
    position :absolute
    left :0
    bottom :0
    right: 0
    padding :.2rem
    background-image :linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.5))
    .banner-album
      display :flex
      justify-content :center
      align-items :center
      background :rgba(0,0,0,0.6)
      width :.8rem
      padding :.1rem .3rem
      border-radius :.28rem
      color :#fff
      font-size :.2rem
      .icon-album
        font-size :.2rem
        padding-right :.1rem
    .banner-title
      font-size :.36rem
      margin-top :.1rem
      color :#fff
</style>
