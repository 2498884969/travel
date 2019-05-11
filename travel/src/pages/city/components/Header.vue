<template>
    <div class="header">
      城市选择
      <router-link to="/">
        <div class="iconfont header-back">&#xe624;</div>
      </router-link>
    </div>
</template>

<script>
    export default {
        name: "CityHeader"
    }
</script>

<style lang="stylus" scoped>
  @import "~styles/variables"

  .header
    position relative
    height $headerHeight
    line-height $headerHeight
    text-align center
    background $bgColor
    color white
    font-size .32 rem
    .header-back
      color #fff
      position absolute
      left 0 rem
      top 0 rem
      width .64 rem
      text-align center
</style>
