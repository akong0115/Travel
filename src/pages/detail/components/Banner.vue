<template>
  <div>
    <div class="banner" @click="openGallery">
        <img
        class="banner-img"
        :src="bannerImg"
        >
        <div class="banner-desc">
          <div class="banner-album">
            <span class="iconfont icon-album">&#xe613;</span>
            <p class="photo-num">{{galleryImgs.length}}</p>
          </div>
          <h1 class="banner-title">{{sightName}}</h1>
        </div>
    </div>
    <fade>
      <banner-gallery :imgs="galleryImgs" @closeGallery="closeGallery" v-show="showGallery" :update="update"></banner-gallery>
    </fade>
  </div>
</template>

<script>
import BannerGallery from 'common/gallery/Gallery'
import Fade from 'common/fade/Fade'
export default {
  naem: 'Banner',
  components: {
    BannerGallery,
    Fade
  },
  data () {
    return {
      showGallery: false
    }
  },
  props: {
    bannerImg: String,
    galleryImgs: Array,
    sightName: String
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
