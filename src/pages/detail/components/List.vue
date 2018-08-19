<template>
  <div>
    <div class="detail-list border-topbottom" v-for="(item,index) of categoryList" :key="index">
      <p class="ticket-info">
        <span class="icon-ticket"></span>
        {{item.title}}
      </p>
      <div class="children" v-if="item.children">
        <detail-list :categoryList="item.children"></detail-list>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'DetailList',
  props: {
    categoryList: Array
  }
}
</script>

<style lang="stylus" scoped>
.detail-list
    .ticket-info
      height :.6rem
      line-height :.6rem
      padding-left :.2rem
      .icon-ticket
        box-sizing :border-box
        display: inline-block
        position: relative
        width: .36rem
        height: .36rem
        left :.04rem
        top :.05rem
        background: url(//s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.45rem no-repeat
        background-size: .4rem 3rem
        margin-right :.2rem
    .children
      padding-left :.2rem
  </style>
