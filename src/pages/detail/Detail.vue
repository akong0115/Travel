<template>
  <div class="detial">
    <banner :bannerImg="bannerImg" :galleryImgs="galleryImgs" :sightName="sightName"></banner>
    <detail-header></detail-header>
    <detail-list :categoryList="categoryList"></detail-list>
  </div>
</template>

<script>
import Banner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
  naem: 'Detail',
  components: {
    Banner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      bannerImg: '',
      categoryList: [],
      galleryImgs: [],
      sightName: '',
      lastId: ''
    }
  },
  methods: {
    getDetailInfo () {
      this.lastId = this.$route.params.id
      axios.get('/api/detail.json', {
        params: {
          id: this.$route.params.id
        }
      }).then(this.getDetailInfoSucc)
    },
    getDetailInfoSucc (res) {
      res = res.data
      console.log(res)
      if (res.ret && res.data) {
        this.bannerImg = res.data.bannerImg
        this.categoryList = res.data.categoryList
        this.galleryImgs = res.data.galleryImgs
        this.sightName = res.data.sightName
      }
    }
  },
  mounted () {
    this.getDetailInfo()
  },
  activated () {
    if (this.lastId !== this.$route.params.id) {
      this.getDetailInfo()
    }
  }
}
</script>

<style lang="stylus" scoped>
  .block
    height :20rem
</style>
