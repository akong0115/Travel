<template>
  <div class="wrapper">
    <swiper :options="swiperOption" >
      <!-- slides -->
      <swiper-slide v-for="item of swiperList" :key="item.id"><img class="swiper-img" :src="item.url"></swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      swiperList: [
        {
          id: 1,
          url: 'http://img1.qunarzz.com/piao/fusion/1807/66/e5a5cec881702f02.jpg_750x200_67bb5691.jpg'
        },
        {
          id: 2,
          url: 'http://img1.qunarzz.com/piao/fusion/1806/3c/c72a1ccd4d7b2202.jpg_750x200_b88bbab4.jpg'
        }
      ]
    }
  }
}
</script>
<style lang="stylus" scoped>
  .wrapper >>>  .swiper-pagination-bullet-active
    background :#fff
  //宽高比例自适应
  .wrapper
    overflow :hidden
    width :100%
    height :0
    padding-bottom :26.7%
    background :#eee
    .swiper-img
      width :100%
</style>
