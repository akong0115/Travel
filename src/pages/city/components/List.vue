<template>
  <section class="list" ref="wrapper">
    <div>
      <div class="location">
        <div class="header border-topbottom">所在位置</div>
        <ul class="location-ul">
          <li class="wrapper">
            <div class="item">{{this.city}}</div>
          </li>
        </ul>
      </div>
      <div class="hot-city">
        <div class="header border-topbottom">热门城市</div>
        <ul class="hot-city-ul">
          <li
            class="wrapper"
            v-for="item of hotCities"
            :key="item.id"
            @click="chooseCity(item.name)"
          >
            <div class="item">{{item.name}}</div>
          </li>
        </ul>
      </div>
      <div
        class="dictionary"
        v-for="(map,key) of cities"
        :key="key"
        :ref="key"
      >
        <div class="header border-topbottom">{{key}}</div>
        <ul class="dictionary-ul">
          <li
            class="dictionary-item border-bottom"
            v-for="item of map"
            :key="item.id"
            @click="chooseCity(item.name)"
          >
            {{item.name}}</li>
        </ul>
      </div>
    </div>
  </section>
</template>

<script>
import BSscroll from 'better-scroll'
import { mapState, mapMutations } from 'vuex'
export default {
  name: 'CityList',
  props: {
    hotCities: Array,
    cities: Object,
    letter: String
  },
  computed: {
    ...mapState(['city'])
  },
  methods: {
    chooseCity (cityName) {
      this.changeCity(cityName)
      this.$router.push('/')
    },
    ...mapMutations(['changeCity'])
  },
  mounted () {
    this.scroll = new BSscroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      this.scroll.scrollToElement(this.$refs[this.letter][0])
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .border-topbottom
    &:before
      border-color :#ccc
    &:after
      border-color :#ccc
  .list
    position :absolute
    top :1.58rem
    left :0
    right :0
    bottom :0
    overflow :hidden
    .header
      line-height :.4rem
      padding-left :.2rem
      background :#eee
      color :$lightTextColor
      font-size :.26rem
    .location-ul
    .hot-city-ul
      padding :.1rem .6rem .1rem .1rem
      overflow :hidden
    .wrapper
      width :33.33%
      float :left
      .item
        text-align :center
        margin :.1rem
        border :.02rem solid #cccccc
        border-radius :.12rem
        padding :.12rem
    .dictionary-ul
      .dictionary-item
        padding :.1rem
        line-height :.36rem
</style>
