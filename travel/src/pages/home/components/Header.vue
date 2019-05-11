<template>
<div class="header">
  <div class="header-left">
    <div class="iconfont back-icon">&#xe624;</div>
  </div>
  <div class="header-input">
    <span class="iconfont">&#xe632;</span>输入城市/景点/游玩/主题
  </div>
  <div class="header-right">
    {{city}}<span class="iconfont icon-arrow">&#xe615;</span>
  </div>
</div>
</template>

<script>
    export default {
        name: "HomeHeader",
        props:{
          city: String
        }
    }

//    1rem = html font-size = 50px

</script>

<style lang="stylus" scoped>
@import '~styles/variables.styl'
  .header
    display: flex
    line-height: .86 rem
    background: $bgColor
    color: #fff
    .header-left
      width: .64 rem
      float: left
      .back-icon
        text-align: center
        font-size: .4 rem
    .header-input
      margin-top: .12rem
      margin-bottom: .12rem
      margin-left: .2 rem
      padding-left: .2 rem
      height: .62 rem
      line-height: .62 rem
      flex: 1
      background: #fff
      border-radius: .1rem
      color: #ccc
    .header-right
      text-align: center
      width: 1.24rem
      float: right
      .icon-arrow
        font-size: .24 rem
</style>
