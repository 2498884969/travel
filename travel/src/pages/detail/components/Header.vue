<template>
  <div>
    <router-link v-show="showAbs" tag="div" to="/" class="header-abs">
      <span class="iconfont header-abs-back">&#xe624;</span>
    </router-link>


    <div v-show="!showAbs" class="header-fixed" :style="opacityStyle">
      景点详情
      <router-link to="/">
        <div class="iconfont header-fixed-back">&#xe624;</div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "DetailHeader",
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll () {
      const top = document.documentElement.scrollTop;
      if(top>60){
        let opacity = top/140;
        opacity = opacity >1 ? 1: opacity;
        this.opacityStyle = {opacity};
        this.showAbs = false
      }else{
        this.showAbs = true
      }

    }
  },
  data() {
    return {
      showAbs: true,
      opacityStyle: {
        opacity: 0
      }
    }
  }
}
</script>

<style lang="stylus" scoped>

  @import "~styles/variables"

  .header-abs
    position absolute
    left .2rem
    top .2rem
    width .8rem
    height .8rem
    border-radius .4rem
    background rgba(0,0,0,.8)
    line-height .8 rem
    text-align center
    .header-abs-back
      color white
      font-size .4 rem
  .header-fixed
    z-index 10 
    position fixed
    top 0
    left 0
    right 0
    height $headerHeight
    line-height $headerHeight
    text-align center
    background $bgColor
    color white
    font-size .32 rem
    .header-fixed-back
      color #fff
      position absolute
      left 0 rem
      top 0 rem
      width .64 rem
      text-align center
</style>
