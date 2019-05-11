<template>
  <div class="search">
    <input type="text" class="search-input" placeholder="请输入汉字或拼音">
  </div>
</template>

<script>
    export default {
        name: "CitySearch"
    }
</script>

<style lang="stylus" scoped>
  @import "~styles/variables"
  .search
    height .72 rem
    background $bgColor
    padding 0 0.1rem
    .search-input
      height 0.62 rem
      line-height 0.62 rem
      box-sizing border-box
      width 100%
      border-radius 0.06 rem
      text-align center
      color #666
      padding 0 0.2rem
</style>
