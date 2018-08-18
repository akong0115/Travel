<template>
  <div>
    <div class="search">
      <input class="search-input" type="text" placeholder="输入城市名或拼音" v-model="keyword">
    </div>
    <ul class="search-result" v-show="keyword" ref="search">
      <div>
        <li class="search-item border-bottom" v-for="item of result" :key="item.id">{{item.name}}</li>
        <li class="search-item border-bottom" v-show="!result.length">没有该城市</li>
      </div>
    </ul>
  </div>
</template>
<script>
import BSscroll from 'better-scroll'
export default {
  name: 'CitySeach',
  data () {
    return {
      keyword: '',
      timer: null,
      result: []
    }
  },
  props: {
    cities: Object
  },
  watch: {
    keyword () {
      let list = []
      if (this.timer) {
        clearTimeout(this.timer)
      }
      this.timer = setTimeout(() => {
        for (let i in this.cities) {
          this.cities[i].forEach(value => {
            if (value.name.indexOf(this.keyword) > -1 || value.spell.indexOf(this.keyword) > -1) {
              list.push(value)
            }
          })
        }
        this.result = list
      }, 100)
    }
  },
  mounted () {
    this.scroll = new BSscroll(this.$refs.search)
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .search
    height :.72rem
    padding :0 .1rem
    background :$bgColor
    .search-input
      width :100%
      height :.62rem
      line-height :.62rem
      padding :0 .1rem
      border-radius :.16rem
      text-align :center
      box-sizing :border-box
      color :#eee
  .search-result
    position :absolute
    top :1.58rem
    left :0
    right :0
    bottom :0
    z-index :2
    background :#fff
    overflow :hidden
    .search-item
      line-height :.44rem
      padding :.1rem
      color :$lightTextColor
</style>
