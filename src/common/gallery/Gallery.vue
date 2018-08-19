<template>
  <div class="Gallery" @click="closeGallery">
    <swiper :options="swiperOption"  ref="mySwiper">
      <swiper-slide class="swiper-slide" v-for="item of imgs" :key="item.index">
        <img class="swiper-img" :src="item">
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'CommonGallery',
  props: {
    imgs: {
      type: Array
    },
    update: Boolean
  },
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        paginationType: 'fraction',
        observe: true,
        observeParents: true
      }
    }
  },
  computed: {
    swiper () {
      return this.$refs.mySwiper.swiper
    }
  },
  methods: {
    closeGallery () {
      this.$emit('closeGallery')
    }
  },
  watch: {
    update () {
      console.log('updateContainerSize')
      this.swiper.onResize()
      // this.swiper.updateContainerSize()
    }
  }
}
</script>

<style lang="stylus" scoped>
  .Gallery >>> .swiper-container
    overflow :inherit
    width :100%
  .Gallery
    z-index :999
    position :fixed
    top :0
    bottom :0
    right :0
    left :0
    background :#000
    display :flex
    justify-content :center
    flex-direction :column
    align-items :center
    .swiper-slide
      .swiper-img
        width :100%
    .swiper-pagination
      position :absolute
      bottom :-1rem
      color :#fff
      width :7.5rem
</style>
