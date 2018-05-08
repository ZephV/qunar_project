<template>
  <div class="search">
    <input class="search-input" type="text" placeholder="输入城市名或拼音">
  </div>
</template>

<script>
export default {
  name: 'CitySearch'
}
</script>

<style lang="stylus" scoped>
  @import '~styles/veribles.styl'
  .search
    height: .76rem
    line-height: .76rem
    background-color: $bgColor
    padding: 0  .1rem
    .search-input
      box-sizing: border-box
      width: 100%
      height: .62rem
      line-height: .62rem
      padding: 0 .1rem
      text-align:center
      color: #666
      border-radius: .06rem
</style>
