<template>
  <div class="header">
    <router-link to='/'>
      <div class="iconfont header-back">&#xe624;</div>
    </router-link>
    城市选择
  </div>
</template>

<script>
export default {
  name: 'CityHeader'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/veribles.styl'
  .header
    overflow: hidden
    position: relative
    height: $headerHeight
    line-height: $headerHeight
    background-color: $bgColor
    text-align: center
    color: #fff
    .header-back
      position: absolute
      top: 0
      left: 0
      width: 0.64rem
      font-size:.4rem
      color: #fff


</style>
