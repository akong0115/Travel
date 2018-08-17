<template>
  <ul class="dictionary">
    <li
      class="item"
      v-for="item of letters"
      :key="item"
      @click="handleClick"
      @touchstart="touchStart"
      @touchmove="touchMove"
      @touchend="touchEnd"
      :ref="item"
    >
    {{item}}</li>
  </ul>
</template>

<script>
export default {
  name: 'DictionaryMap',
  props: {
    cities: Object
  },
  data () {
    return {
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  computed: {
    letters () {
      let letters = []
      if (this.cities) {
        for (let i in this.cities) {
          letters.push(i)
        }
      }
      return letters
    }
  },
  methods: {
    handleClick (e) {
      this.$emit('change', e.target.innerText)
    },
    touchStart () {
      this.touchStatus = true
    },
    touchMove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          let moveOffset = e.touches[0].clientY - 79
          let index = Math.floor((moveOffset - this.startY) / 20)
          this.$emit('change', this.letters[index])
        }, 16)
      }
    },
    touchEnd () {
      this.touchStatus = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .dictionary
    position :absolute
    top :1.58rem
    bottom :0
    right :0
    display :flex
    flex-direction :column
    justify-content :center
    width :.4rem
    .item
      color :$bgColor
      line-height :.4rem
</style>
