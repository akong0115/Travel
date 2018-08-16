<template>
  <div class="recommend">
    <div class="recommend-title">周末去哪儿</div>
    <ul class="recommend-items">
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <div class="img-wrapper">
          <img class="item-img" :src="item.url">
        </div>
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [
        {
          id: 1,
          url: 'http://img1.qunarzz.com/sight/source/1505/4e/3e87ee62e59cdb.jpg_r_640x214_fe6cc902.jpg',
          title: '上海迪士尼乐园',
          desc: '上海迪士尼乐园快乐童话暑假，带你畅游迪士尼世界'
        },
        {
          id: 2,
          url: 'http://img1.qunarzz.com/sight/source/1505/4e/3e87ee62e59cdb.jpg_r_640x214_fe6cc902.jpg',
          title: '上海迪士尼乐园',
          desc: '上海迪士尼乐园快乐童话暑假，带你畅游迪士尼世界'
        },
        {
          id: 3,
          url: 'http://img1.qunarzz.com/sight/source/1505/4e/3e87ee62e59cdb.jpg_r_640x214_fe6cc902.jpg',
          title: '上海迪士尼乐园',
          desc: '上海迪士尼乐园快乐童话暑假，带你畅游迪士尼世界'
        },
        {
          id: 4,
          url: 'http://img1.qunarzz.com/sight/source/1505/4e/3e87ee62e59cdb.jpg_r_640x214_fe6cc902.jpg',
          title: '上海迪士尼乐园',
          desc: '上海迪士尼乐园快乐童话暑假，带你畅游迪士尼世界'
        },
        {
          id: 5,
          url: 'http://img1.qunarzz.com/sight/source/1505/4e/3e87ee62e59cdb.jpg_r_640x214_fe6cc902.jpg',
          title: '上海迪士尼乐园',
          desc: '上海迪士尼乐园快乐童话暑假，带你畅游迪士尼世界'
        },
        {
          id: 6,
          url: 'http://img1.qunarzz.com/sight/source/1505/4e/3e87ee62e59cdb.jpg_r_640x214_fe6cc902.jpg',
          title: '上海迪士尼乐园',
          desc: '上海迪士尼乐园快乐童话暑假，带你畅游迪士尼世界'
        }
      ]
    }
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .recommend
    .recommend-title
      background :#eee
      line-height :.72rem
      height :.72rem
      padding-left :.2rem
    .recommend-items
      .item
        .img-wrapper
          overflow :hidden
          width :100%
          height :0
          padding-bottom :33.9%
        .item-info
          flex :1
          padding :.1rem
          min-width :0
          .item-title
            line-height :.44rem
            height :.44rem
            ellipsis()
          .item-desc
            line-height :.44rem
            height :.44rem
            color :#ccc
            ellipsis()
</style>
