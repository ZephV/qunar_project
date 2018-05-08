<template>
  <div>
    <div class="title">周末去哪玩</div>
    <div class="item border-bottom" v-for="item of list" :key="item.id">
      <div class="item-img-wrapper">
        <img :src="item.imgUrl" alt="" class="item-img">
      </div>
      <div class="item-info">
        <p class="item-title">{{item.title}}</p>
        <p class="item-desc">{{item.desc}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
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
    .item-img-wrapper
      overflow: hidden
      height: 0
      padding-bottom: 33.9%
      .item-img
        width: 100%
    .item-info
      padding: .1rem
      .item-title
        line-height: .54rem
        font-size: .33rem
        font-weight: bold
        ellipsis()
      .item-desc
        line-height: .44rem
        color:#888
        ellipsis()
</style>
