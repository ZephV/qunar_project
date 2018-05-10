<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="btn-list">
          <div class="btn-wrapper">
            <div class="btn">深圳</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="btn-list">
          <div class="btn-wrapper"  v-for="item of hot" :key="item.id">
            <div class="btn">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(item,key) of cities" :key="key" :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
          <div class="item border-bottom" v-for="innerItem of item" :key="innerItem.id">{{innerItem.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  props: {
    hot: Array,
    cities: Object,
    letter: String
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  },
  watch: {
    letter () {
      const element = this.$refs[this.letter][0]
      this.scroll.scrollToElement(element)
    }
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/veribles.styl'
  .border-topbottom
    &:before
      border-color: #cccccc
    &:after
      border-color: #cccccc
  .border-bottom
    &:after
      border-color: #cccccc
  .list
    position: absolute
    top: 1.62rem
    left: 0
    right: 0
    bottom: 0
    overflow: hidden
    .title
      line-height: .54rem
      background-color: #eeeeee
      padding-left: .2rem
      color: #666
      font-size: .26rem
    .btn-list
      padding: .1rem .6rem .1rem .1rem
      overflow: hidden
      .btn-wrapper
        float: left
        width: 33.33%
        .btn
          margin: .1rem
          padding: .1rem 0
          text-align: center
          border: .02rem solid #ccc
          border-radius: .06rem
    .item-list
      .item
        line-height: .76rem
        padding-left: .2rem
</style>
