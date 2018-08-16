<template>
  <div class="recommend">
    <div class="recommend-title">热门推荐</div>
    <ul class="recommend-items">
      <li class="item border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="item-img" :src="item.url">
        <div class="item-info">
          <p class="item-title">{{item.title}}</p>
          <p class="item-desc">{{item.desc}}</p>
          <button class="desc-btn">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [
        {
          id: 1,
          url: 'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
          title: '上海迪士尼乐园',
          desc: '上海迪士尼乐园快乐童话暑假，带你畅游迪士尼世界'
        },
        {
          id: 2,
          url: 'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
          title: '上海迪士尼乐园',
          desc: '上海迪士尼乐园快乐童话暑假，带你畅游迪士尼世界'
        },
        {
          id: 3,
          url: 'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
          title: '上海迪士尼乐园',
          desc: '上海迪士尼乐园快乐童话暑假，带你畅游迪士尼世界'
        },
        {
          id: 4,
          url: 'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
          title: '上海迪士尼乐园',
          desc: '上海迪士尼乐园快乐童话暑假，带你畅游迪士尼世界'
        },
        {
          id: 5,
          url: 'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
          title: '上海迪士尼乐园',
          desc: '上海迪士尼乐园快乐童话暑假，带你畅游迪士尼世界'
        },
        {
          id: 6,
          url: 'http://img1.qunarzz.com/sight/p0/1607/7c/7cda8b6782dabd80b4.img.jpg_200x200_2039e660.jpg',
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
        display :flex
        .item-img
          height :1.7rem
          width :1.7rem
          padding :.1rem
        .item-info
          flex :1
          padding :.1rem
          min-width :0
          .item-title
            line-height :.44rem
            height :.44rem
            margin-top :.1rem
            ellipsis()
          .item-desc
            line-height :.44rem
            height :.44rem
            color :#ccc
            ellipsis()
          .desc-btn
            background :#ff9300
            border-radius :.06rem
            color :#fff
            padding :0 .1rem
            line-height :.44rem
            margin-top :.1rem
</style>
