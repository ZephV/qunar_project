<template>
    <div>
      <router-link to="/" tag="div" class="header-abs" v-show="showAbs">
        <div class="iconfont header-abs-back">&#xe624;</div>
      </router-link>
      <div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
        <router-link to='/'>
          <div class="iconfont header-fixed-back">&#xe624;</div>
        </router-link>
        景点详情
      </div>
    </div>
</template>

<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop
      if (top > 60) {
        let opacity = top / 140
        opacity = opacity > 140 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showAbs = false
      } else {
        this.showAbs = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>

<style lang="stylus" scoped>
  @import '~styles/veribles.styl'
  .header-abs
    position: absolute
    top: .2rem
    left: .2rem
    height: .8rem
    width: .8rem
    line-height: .8rem
    text-align: center
    border-radius: .4rem
    background-color: rgba(0,0,0,.8)
    .header-abs-back
      color: #fff
      font-size: .4rem
  .header-fixed
    position: fixed
    top: 0
    left: 0
    right: 0
    z-index:2
    overflow: hidden
    height: $headerHeight
    line-height: $headerHeight
    background-color: $bgColor
    text-align: center
    color: #fff
    .header-fixed-back
      position: absolute
      top: 0
      left: 0
      width: 0.64rem
      font-size:.4rem
      color: #fff
</style>
