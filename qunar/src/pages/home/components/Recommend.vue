<template>
  <div>
    <div class="title">热销景点</div>
    <div class="item border-bottom" v-for="item of list" :key="item.id">
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
  props: {
    list: Array
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
