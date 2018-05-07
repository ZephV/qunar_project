<template>
  <div>
    <div class="title">热销景点</div>
    <div class="item border-bottom" v-for="item of recommendList" :key="item.id">
      <img :src="item.imgUrl" alt="" class="item-img">
      <div class="item-info">
        <p class="item-title">{{item.title}}</p>
        <p class="item-desc">{{item.desc}}</p>
        <button class="item-btn">查看详情</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [{
        title: '深圳小梅沙海洋世界',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1804/3d/3da274777b963b2a3.water.jpg_200x200_aef4339e.jpg',
        id: '01',
        desc: '深圳小梅沙海洋世界深圳小梅沙海洋世界'
      },
      {
        title: '深圳小梅沙海洋世界',
        imgUrl: 'http://img1.qunarzz.com/sight/p0/1804/3d/3da274777b963b2a3.water.jpg_200x200_aef4339e.jpg',
        id: '02',
        desc: '深圳小梅沙海洋世界深圳小梅沙海洋世界'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
  .title
    line-height: .8rem
    background:#ccc
    text-indent: .2rem
  .item
    overflow: hidden
    display: flex
    height: 1.9rem
    .item-img
      height 1.7rem
      width: 1.7rem
      padding: .1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
      .item-title
        line-height: .54rem
        font-size: .33rem
        font-weight: bold
        ellipsis()
      .item-desc
        line-height: .44rem
        color:#888
        ellipsis()
      .item-btn
        margin-top: .2rem
        background-color: #ff9300
        padding:0 .2rem
        border-radius: .06rem
</style>
